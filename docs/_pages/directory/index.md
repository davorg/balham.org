---
title: "Business Directory"
permalink: /directory/
---

    <div id="business-list"></div>

    <script>
        fetch('https://balham.org/data/businesses.json')
            .then(response => response.json())
            .then(data => {
                const container = document.getElementById('business-list');
                data.forEach(business => {
                    const div = document.createElement('div');
                    div.className = 'business';
                    div.innerHTML = `
                        <h2>${business.name}</h2>
                        <p><strong>Category:</strong> ${business.category}</p>
                        <p><strong>Address:</strong> ${business.address}</p>
                        <p><a href="${business.website}" target="_blank">${business.website ? "Visit Website" : ""}</a></p>
                        <p>${business.description}</p>
                        <hr>
                    `;
                    container.appendChild(div);
                });
            })
            .catch(error => console.error('Error loading businesses:', error));
    </script>
