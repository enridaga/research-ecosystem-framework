---
container-id: reeco-framework
type: Project
work-package:
- WP1
pilot:
- polifonia-ecosystem
funder:
  - name: Horizon 2020 Framework Programme
    url: https://cordis.europa.eu/programme/id/H2020-EC
    grant-agreement: "https://cordis.europa.eu/project/id/101004746"
credits: "This project has received funding from the European Union’s Horizon 2020 research and innovation programme under grant agreement N. 101004746."
layout: default
title: Home
nav_order: 0
permalink: /
ecosystem-release: v1.0
---

# Research Ecosystem ({{ page.ecosystem-release }})
{: .fs-9 }

The Research Ecosysten Website template. 
{: .fs-6 .fw-300 }

---

Describe here your research ecosystem
 
{% assign types =  site.documents  | map: 'type' | join: ','  | split: ',' | uniq | sort %}

The ecosystem includes {% assign types_data = "Data,Dataset,Schema,Repository,Registry,Ontology,Corpus,Lexicon,KnowledgeGraph" | split: "," %}{% assign ncomponents = site.documents  | where_exp: 'item',"types_data contains item.type" | size %} {{ncomponents}} <a href="data.html">data</a>, {% assign software_data = "Software,Workflow,API,UserInterface,SofwareLibrary,DockerImageContainer,Notebook,Script,Application,Website,WebApplication,WebService,SPARQLEndpoint,MobileApp,CLITool" | split: "," %} {% assign ncomponents = site.documents  | where_exp: 'item',"software_data contains item.type" | size %} {{ncomponents}} <a href="software.html">tools</a>, {% assign report_data = "Report,RequirementsCollection,Story,Persona,Mockup,Surbey,InPresenceGroup,Documentation,Tutorial,EvaluationReport" | split: "," %}{% assign ncomponents = site.documents  | where_exp: 'item',"report_data contains item.type" | size %} and {{ncomponents}} <a href="report.html">reports</a>.

Project content is managed on [GitHub](http://github.com/{{ site.github }}).


<div id="chart_container_data"></div>
<script>
anychart.onDocumentReady(function() {
    // set the data
    var data = [
		{% for type in types %}
			{% if type != "" %}
				{% assign comps =  site.documents  | where: 'type',type | size%}
				{% if comps > 0 %}
     		   		{x: "{{type}}", value: {{ comps }} },
				{% endif %}
			{% endif %}
		{% endfor %}
    ];
    // create the chart
    var chart = anychart.pie3d();
    // set the chart title
    // chart.title("Polifonia Project Components by Type");
	// add the data
    chart.data(data);
	// sort elements
    chart.sort("desc");  
	// set legend position
    chart.legend().position("right");
	// set items layout
    chart.legend().itemsLayout("vertical");
	// display the chart in the container
    chart.container('chart_container_data');
    chart.draw();
  });
  </script>

{% for type in types %}
{% if type != "" %}
{% assign components =  site.documents  | where: 'type',type %}
{% assign numberOf = components | size %}
{% if numberOf > 0 %}
### {{ type }}

There are {{numberOf}} components of type {{type}}:
	{% for component in components %}
- [{% if component.name %}{{ component.name }}{%else%}{{ component.component-id}} {%endif%}]({{ component.url | relative_url }})	{% endfor %}	
{% endif %}
{% endif %}
{% endfor %}

