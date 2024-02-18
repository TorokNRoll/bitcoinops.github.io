{% capture /dev/null %}

{% if include.state == "true" and include.state3 == "true" %}
  {% assign cell_emoji = "&#x1F4B8;" %}  <!--- Send Support --->
  {% if include.state2 == "true" or include.state4 == "true" %}
      {% assign cell_emoji = "&#x2705;" %}  <!--- Full Support --->
  {% endif %}
{% elsif include.state == "false" %}
  {% assign cell_emoji = "&#x274C;" %}  <!--- No Support --->
{% else %}
    {% assign cell_emoji = "&#x2796;" %} <!--- Not Applicable --->
{% endif %}

{% endcapture %}

<td><a>{{cell_emoji}}</a></td>
