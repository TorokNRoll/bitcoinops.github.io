{% capture /dev/null %}
{% assign cell_style = "default" %}
{% assign cell_label = "" %}
{% case include.state %}
  {% when "true" %}
    {% assign cell_emoji = "&#x1F4B8;" %}
    {% case include.state2 %}
      {% when "true" %}
        {% assign cell_emoji = "&#x2705;" %}
    {% endcase %}  
  {% when "false" %}
    {% assign cell_emoji = "&#x274C;" %}
  {% when "na" %}
    {% assign cell_label = "-" %}
  {% when "untested" %}
    {% assign cell_label = "?" %}
  {% else %}{% include ERROR_43_unexpected_value %}
{% endcase %}
{% endcapture %}


<td><a>{{cell_emoji}}</a></td>
