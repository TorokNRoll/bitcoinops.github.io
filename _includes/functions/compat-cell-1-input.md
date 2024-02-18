{% capture /dev/null %}



{% if include.state == "true" %}
  {% assign cell_emoji = "&#x2705;" %} <!--- Full Support --->
{% elsif include.state == "false" %}
  {% assign cell_emoji = "&#x274C;" %}  <!--- No Support --->
{% else %}
    {% assign cell_emoji = "&#x2796;" %} <!--- Not Applicable --->
{% endif %}


{% endcapture %}

<td><a>{{cell_emoji}}</a></td>
