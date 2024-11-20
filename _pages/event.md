---
permalink: /winter-school-2024/
layout: splash
author_profile: false
header:
  overlay_color: "#00618F"
title: "<b><center>Goethe University - Tel Aviv University Winterschool <br> Adaptive Cognition in Noisy Environments</center></b>"
excerpt: <p style="color:white;text-align:center;font-weight:bold;">Goethe University Frankfurt, Dec. 2 - Dec. 5 2024</p>
---
<style>
.speaker-link {
    color: var(--primary-color);
    text-decoration: none;
    cursor: pointer;
}

.speaker-link:hover {
    text-decoration: underline;
}

.speaker-cards {
    margin-bottom: 1rem;
    cursor: pointer;
    transition: transform 0.3s ease, box-shadow 0.3s ease;
    border: 2px solid transparent;
}

.custom-card {
    cursor: pointer;
    transition: transform 0.3s ease, box-shadow 0.3s ease;
    border: 2px solid transparent;
    box-shadow: 0 4px 8px rgba(0,0,0,0.1);
    background-color: white;
    padding: 1rem;
    display: flex;
    flex-direction: column;
    align-items: center;
    height: 220px; /* Ensure consistent height */
}

.custom-card.active {
    border-color: var(--primary-color);
    box-shadow: 0 6px 12px rgba(0,0,0,0.2);
}

.speaker-details {
    background: white;
    padding: 2rem;
    border-radius: 10px;
    margin-top: 2rem;
    box-shadow: 0 5px 15px rgba(0,0,0,0.1);
    display: none;
    animation: fadeIn 0.3s ease;
}

.speaker-details.show {
    display: block;
}

@keyframes fadeIn {
    from { opacity: 0; transform: translateY(-20px); }
    to { opacity: 1; transform: translateY(0); }
}

.speaker-link {
    color: var(--primary-color);
    text-decoration: none;
    cursor: pointer;
}

.speaker-link:hover {
    color: var(--accent-color);
    text-decoration: underline;
}

.image-container img {
    width: 250px;
    height: auto;
}
</style>

<!-- Speaker Cards Section -->
<div class="row mb-4">
    <div class="col-md-12">
        <h5 class="section-title">Speakers</h5>
        <div class="row speaker-cards">
        {% for speaker in site.data.winter_school_speakers %}
            <div class="col-md-3 mb-3">
                <div class="custom-card" data-speaker-id="{{ speaker.id }}">
                    <div class="card-body text-center">
                        {% if speaker.picture %}
                            <img src="{{ speaker.picture }}" class="img-fluid rounded-circle speaker-image mb-3" alt="{{ speaker.name }}">
                        {% else %}
                            <i class="fas fa-user-circle icon-feature"></i>
                        {% endif %}
                        <h6>{{ speaker.name }}</h6>
                        <p class="text-muted">{{ speaker.affiliation }}</p>
                    </div>
                </div>
            </div>
        {% endfor %}
        </div>

        <!-- Speaker Details Section -->
        {% for speaker in site.data.winter_school_speakers %}
            <div id="speaker-details-{{ speaker.id }}" class="speaker-details">
                <h4>{{ speaker.name }}</h4>
                <p class="text-muted">{{ speaker.affiliation }}</p>
                <div class="mt-4">
                    <p>{{ speaker.bio }}</p>
                    {% if speaker.title %}
                        <h5 class="mt-4">{{ speaker.title }}</h5>
                    {% endif %}
                    {% if speaker.abstract %}
                        <p class="mt-3">{{ speaker.abstract }}</p>
                    {% endif %}
                </div>
            </div>
        {% endfor %}
    </div>
</div>

<!-- Schedule Section -->
<div class="row mb-4">
    <div class="col-md-12">
        <div class="card-body">        
            <section id="schedule">
                <h5 class="section-title">Schedule</h5>
                {% for day in site.data.winter_school_schedule %}
                    <div class="schedule-day">
                        <div class="schedule-day-header">
                            <h5>{{ day.date }}</h5>
                            <span class="expand-icon">▼</span>
                        </div>
                        <div class="schedule-day-content">
                            {% for session in day.sessions %}
                                <div class="schedule-session">
                                    <p class="schedule-time">{{ session.time }}</p>
                                    <h6>{{ session.title }}</h6>
                                    {% for item in session.items %}
                                        <p>
                                        {% assign processed_item = item %}
                                        {% for speaker in site.data.winter_school_speakers %}
                                            {% assign speaker_full_name = speaker.name %}
                                            {% assign speaker_short_name = speaker.name | remove: "Prof. Dr. " %}
                                            {% if item contains speaker_full_name or item contains speaker_short_name %}
                                                {% capture speaker_link %}
                                                    <a class="speaker-link" data-speaker-id="{{ speaker.id }}" href="#">{{ speaker_short_name }}</a>
                                                {% endcapture %}
                                                {% assign processed_item = processed_item | replace: speaker_full_name, speaker_link | replace: speaker_short_name, speaker_link %}
                                            {% endif %}
                                        {% endfor %}
                                        {{ processed_item }}
                                        </p>
                                    {% endfor %}
                                </div>
                            {% endfor %}
                        </div>
                    </div>
                {% endfor %}
            </section>
        </div>
    </div>
</div>

<!-- Sponsors Section -->
<div class="row mb-4">
    <div class="col-md-12">
        <h5 class="section-title">Sponsors</h5>        
        <div class="image-container">
            <a href="https://www.german-u15.de/"><img src="/assets/images/winterschool/German_U15.png" alt="GermanU15 Logo" ></a>
            <a href="https://www.gif.org.il/"><img src="/assets/images/winterschool/giflogo.png" alt="GIF Logo"></a>
            <a href="https://www.minerva.mpg.de/80020/minerva-center-for-human-intelligence-in-immersive-augmented-and-mixed-realities"><img src="/assets/images/winterschool/minervacenter.png" alt="minervacenter Logo"></a>
        </div>
    </div>
</div>    

<br>

<!-- JavaScript -->
<script>
document.addEventListener('DOMContentLoaded', function() {
    // Schedule day toggle functionality
    const dayHeaders = document.querySelectorAll('.schedule-day-header');
    dayHeaders.forEach(header => {
        header.addEventListener('click', function() {
            this.classList.toggle('active');
            const content = this.nextElementSibling;
            if (content) {
                content.classList.toggle('show');
                const icon = this.querySelector('.expand-icon');
                if (icon) {
                    icon.textContent = icon.textContent === '▼' ? '▲' : '▼';
                }
            }
        });
    });

    // Event delegation for speaker links in schedule
    document.addEventListener('click', function(e) {
        if (e.target.classList.contains('speaker-link')) {
            e.preventDefault();
            const speakerId = e.target.dataset.speakerId;
            if (speakerId) {
                showSpeakerDetails(speakerId);
            }
        }
    });

    // Add click event listeners to speaker cards
    const speakerCards = document.querySelectorAll('.custom-card');
    speakerCards.forEach(card => {
        card.addEventListener('click', function() {
            const speakerId = this.dataset.speakerId;
            if (speakerId) {
                showSpeakerDetails(speakerId);
            }
        });
    });
});

function showSpeakerDetails(speakerId) {
    try {
        // Reset previous states
        document.querySelectorAll('.custom-card').forEach(card => {
            card.classList.remove('active');
        });
        document.querySelectorAll('.speaker-details').forEach(detail => {
            detail.classList.remove('show');
        });

        // Activate selected speaker card and details
        const speakerCard = document.querySelector(`.custom-card[data-speaker-id="${speakerId}"]`);
        const speakerDetails = document.getElementById(`speaker-details-${speakerId}`);

        if (!speakerCard || !speakerDetails) {
            console.error('Speaker card or details not found for ID:', speakerId);
            return;
        }

        speakerCard.classList.add('active');
        speakerDetails.classList.add('show');

        // Scroll to speaker details
        speakerDetails.scrollIntoView({
            behavior: 'smooth',
            block: 'start'
        });
    } catch (error) {
        console.error('Error displaying speaker details:', error);
        alert('Sorry, there was an error displaying the speaker details.');
    }
}
</script>