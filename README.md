jquery.selectbox-0.2
====================

Custom select box replacement inspired by jQuery UI source. Require jQuery 1.4.x -  jQuery 1.7.x


There is an error on "_changeSelectbox" function replace this function...

_changeSelectbox: function (target, value, text) {
  var onChange,
  inst = this._getInst(target);
  if (inst) {
    onChange = this._get(inst, 'onChange');
    $("#sbSelector_" + inst.uid).text(text);
  }
  value = value.replace(/\'/g, "\\'");
  //before add the selected attribute, will search the other options that has selected attribute and remove;
  $(target).find("option[selected='selected']").removeAttr("selected");
  //Add the selected attribute to the option
  $(target).find("option[value='" + value + "']").attr("selected", "selected");
  if (inst && onChange) {
    onChange.apply((inst.input ? inst.input[0] : null), [value, inst]);
  }else if (inst && inst.input) {
    inst.input.trigger('change');
  }
},
