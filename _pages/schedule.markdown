---
# Feel free to add content and custom Front Matter to this file.
# To modify the layout, see https://jekyllrb.com/docs/themes/#overriding-theme-defaults

layout: default-full
title: "Home"
show_sidetoc: true
subtitle: "21-27 June 2026 – Baratti (Piombino) – TUSCANY (Italy)"
header_title: "Data Analysis and AI <br>in Sport, Health and Wellbeing"
---

<style>
.card-header .btn[aria-expanded="true"] .fa-plus {
    display: none !important;
}
.card-header .btn[aria-expanded="true"] .fa-minus {
    display: inline !important;
}
.accordion-toggle {
    margin-right: 0.5rem;
    font-size: 0.875rem;
}
</style>

<div class="full-width-wrapper">
    <img src="{{ site.baseurl }}/assets/images/header.svg" alt="sbd-pattern" class="full-width-image">
</div>

<div class="registration">
    <div class="container">
        <div class="row pt-2 ">
            <div class="col-md-8 offset-md-2 col-sm-12">
                <h2>Detailed Program</h2>
                <hr>
                <p class="lead">
                    The school is organized in two parts: in the morning students will attend lectures with different speakers, while in the afternoon they will work on group projects guided by dedicated tutors.
                </p>
                <hr>
            </div>
        </div>
    </div>

</div>

<div class="container">
        <div class="row py-3">
            <div class="col-12">
                <div class="program-table">
                <table>
  <thead>
    <tr>
    {% for header in site.data.schedule.headers %}
      <th>{{ header | markdownify }}</th>
    {% endfor %}
    </tr>
  </thead>
  <tbody>
    {% for activity in site.data.schedule.activities %}
      <tr {% if activity.class %}class="{{ activity.class }}"{% endif %}>
        <td>{{ activity.time | markdownify }}</td>
        {% if activity.sunday.content %}
          <td rowspan="{{ activity.sunday.rowspan }}"><i class='fas fa-{{ activity.sunday.content.icon }}'></i> {{ activity.sunday.content.text | markdownify }}</td>
        {% elsif activity.sunday %}
          <td><i class='fas fa-{{ activity.sunday.icon }}'></i> {{ activity.sunday.text | markdownify }}</td>
        {% endif %}
        {% if activity.monday.content %}
          <td rowspan="{{ activity.monday.rowspan }}"><i class='fas fa-{{ activity.monday.content.icon }}'></i> {{ activity.monday.content.text | markdownify }}</td>
        {% elsif activity.monday %}
          <td><i class='fas fa-{{ activity.monday.icon }}'></i> {{ activity.monday.text | markdownify }}</td>
        {% endif %}
        {% if activity.tuesday.content %}
          <td rowspan="{{ activity.tuesday.rowspan }}"><i class='fas fa-{{ activity.tuesday.content.icon }}'></i> {{ activity.tuesday.content.text | markdownify }}</td>
        {% elsif activity.tuesday %}
          <td><i class='fas fa-{{ activity.tuesday.icon }}'></i> {{ activity.tuesday.text | markdownify }}</td>
        {% endif %}
        {% if activity.wednesday.content %}
          <td rowspan="{{ activity.wednesday.rowspan }}"><i class='fas fa-{{ activity.wednesday.content.icon }}'></i> {{ activity.wednesday.content.text | markdownify }}</td>
        {% elsif activity.wednesday %}
          <td><i class='fas fa-{{ activity.wednesday.icon }}'></i> {{ activity.wednesday.text | markdownify }}</td>
        {% endif %}
        {% if activity.thursday.content %}
          <td rowspan="{{ activity.thursday.rowspan }}"><i class='fas fa-{{ activity.thursday.content.icon }}'></i> {{ activity.thursday.content.text | markdownify }}</td>
        {% elsif activity.thursday %}
          <td><i class='fas fa-{{ activity.thursday.icon }}'></i> {{ activity.thursday.text | markdownify }}</td>
        {% endif %}
        {% if activity.friday.content %}
          <td rowspan="{{ activity.friday.rowspan }}"><i class='fas fa-{{ activity.friday.content.icon }}'></i> {{ activity.friday.content.text | markdownify }}</td>
        {% elsif activity.friday %}
          <td><i class='fas fa-{{ activity.friday.icon }}'></i> {{ activity.friday.text | markdownify }}</td>
        {% endif %}                        
      </tr>
    {% endfor %}
  </tbody>
</table>
            </div>
        </div>
    </div>

</div>


<div class="registration">
    <div class="container">
        <div class="row pt-2 ">
            <div class="col-md-8 offset-md-2 col-sm-12">
                <h2>Daily Program</h2>
                <hr>
                <div id="daysAccordion">
                {% for day_info in site.data.school-info.days %}
                <div class="card">
                    <div class="card-header" id="heading{{ forloop.index }}">
                        <h5 class="mb-0">
                            <button class="btn btn-link" type="button" data-toggle="collapse" data-target="#collapse{{ forloop.index }}" aria-expanded="{% if forloop.first %}true{% else %}false{% endif %}" aria-controls="collapse{{ forloop.index }}" style="font-size: 1.25rem; color: #07286E; text-decoration: none;">
                                <span class="accordion-toggle">
                                    <i class="fas fa-plus"></i>
                                    <i class="fas fa-minus" style="display: none;"></i>
                                </span>
                                {{ day_info.day }}
                            </button>
                        </h5>
                    </div>
                    <div id="collapse{{ forloop.index }}" class="collapse{% if forloop.first %} show{% endif %}" aria-labelledby="heading{{ forloop.index }}" data-parent="#daysAccordion">
                        <div class="card-body">
                            {{ day_info.description | markdownify }}
                        </div>
                    </div>
                </div>
                {% endfor %}
            </div>
            </div>
        </div>
    </div>

</div>
<br>

<script>
document.addEventListener('DOMContentLoaded', function() {
  const headings = document.querySelectorAll('h1, h2, h3, h4, h5, h6');
  headings.forEach(function(heading) {
    if (!heading.id) {
      let text = heading.textContent.trim();
      let id = text
        .toLowerCase()
        .replace(/[^\w\s-]/g, '') 
        .replace(/\s+/g, '-')
        .replace(/-+/g, '-');
      heading.id = id;
    }
  });
  
  const table = document.querySelector('.program-table table');
  if (!table) return;
  
  const tbody = table.querySelector('tbody');
  if (!tbody) return;
  
  const rows = tbody.querySelectorAll('tr');
  const virtualTable = [];
  
  for (let i = 0; i < rows.length; i++) {
    virtualTable[i] = [];
  }
  
  let rowIndex = 0;
  rows.forEach(row => {
    let colIndex = 0;
    
    Array.from(row.cells).forEach(cell => {
      while (virtualTable[rowIndex][colIndex]) {
        colIndex++;
      }
      
      const rowspan = parseInt(cell.getAttribute('rowspan')) || 1;
      const colspan = parseInt(cell.getAttribute('colspan')) || 1;
      
      for (let i = 0; i < rowspan; i++) {
        for (let j = 0; j < colspan; j++) {
          if (!virtualTable[rowIndex + i]) {
            virtualTable[rowIndex + i] = [];
          }
          virtualTable[rowIndex + i][colIndex + j] = {
            cell: cell,
            originalRow: rowIndex,
            originalCol: colIndex
          };
        }
      }
      
      colIndex += colspan;
    });
    
    rowIndex++;
  });
  
  for (let i = 0; i < virtualTable.length; i++) {
    for (let j = 1; j < virtualTable[i].length; j++) {
      const cellInfo = virtualTable[i][j];
      if (!cellInfo) continue;
      
      const timeCell = virtualTable[i][0]?.cell;
      if (!timeCell) continue;
      
      cellInfo.cell.addEventListener('mouseenter', function() {
        timeCell.classList.add('highlight-time-cell');
      });
      
      cellInfo.cell.addEventListener('mouseleave', function() {
        timeCell.classList.remove('highlight-time-cell');
      });
    }
  }
});
</script>