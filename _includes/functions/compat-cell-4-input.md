{% capture /dev/null %}

{% if include.state == "Full Support (send & receive)" or include.state == "Send Support" %}
  {% if include.state2 == "Full Support (send & receive)" or include.state2 == "Send Support" %}
      {% assign cell_emoji = "&#x1F4B8;" %}  <!--- Send Support --->
          {% if include.state == "Full Support (send & receive)" or include.state2 == "Full Support (send & receive)" %}      
              {% assign cell_emoji = "&#x2705;" %}  <!--- Full Support --->
          {% endif %}
  {% endif %}
{% elsif include.state == "No Support" %}
  {% assign cell_emoji = "&#x274C;" %}  <!--- No Support --->
{% elsif include.state == "Not Applicable" %}
    {% assign cell_emoji = "&#x2796;" %} <!--- Not Applicable --->
{% endif %}

{% endcapture %}

<td><a>{{cell_emoji}}</a></td>
