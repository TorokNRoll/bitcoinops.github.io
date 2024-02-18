{% capture /dev/null %}
{% assign cell_style = "default" %}
{% assign cell_label = "" %}
{% case include.state %}
  {% when "true" %}
    {% assign cell_style = "compat_yes" %}
    {% assign cell_label = yes %}
  {% when "false" %}
    {% assign cell_style = "compat_no" %}
    {% assign cell_label = no %}
  {% when "na" %}
    {% assign cell_label = "-" %}
  {% when "untested" %}
    {% assign cell_label = "?" %}
  {% else %}{% include ERROR_43_unexpected_value %}
{% endcase %}
{% endcapture %}<td class="compat {{cell_style}}"><a href="{{tool.internal_url}}{{include.anchor}}">{{cell_label}}{{include.state}}{{include.state2}}</a></td>

<!--- Need to be able to test for multiple states.  if states > 1 then each applicable state must be true for a check.-->
