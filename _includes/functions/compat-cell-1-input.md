{% capture /dev/null %}



{% if include.state == "Full Support (send & receive)" %}
  {% assign cell_emoji = "&#x2705;" %} <!--- Full Support --->
{% elsif include.state == "Send Support" %}
  {% assign cell_emoji = "&#x1F4B8;" %}  <!--- Send Support --->
{% elsif include.state == "No Support" %}
  {% assign cell_emoji = "&#x274C;" %}  <!--- No Support --->
{% elsif include.state == "Not Applicable" %}
  {% assign cell_emoji = "&#x2796;" %} <!--- Not Applicable --->
{% elsif include.state == "Yes" %}
  {% assign cell_emoji = "&#x2705;" %} <!--- Yes --->
{% elsif include.state == "No" %}
  {% assign cell_emoji = "&#x274C;" %} <!--- No --->
{% endif %}

{% endcapture %}

<td><a>{{cell_emoji}}</a></td>
