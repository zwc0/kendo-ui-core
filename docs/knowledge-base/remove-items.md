---
title: Remove DropDownList Items
page_title: Remove DropDownList Items
description: "Learn how to remove items from a Kendo UI DropDownList widget."
previous_url: /controls/editors/dropdownlist/how-to/remove-items, /controls/editors/dropdownlist/how-to/editing/remove-items
slug: howto_remove_items_dropdownlist
tags: telerik, kendo, jquery, dropdownlist, remove, items
component: dropdownlist
type: how-to
res_type: kb
---

## Environment

<table>
 <tr>
  <td>Product</td>
  <td>Progress Kendo UI DropDownList for jQuery</td>
 </tr>
 <tr>
  <td>Operating System</td>
  <td>Windows 10 64bit</td>
 </tr>
 <tr>
  <td>Visual Studio version</td>
  <td>Visual Studio 2017</td>
 </tr>
 <tr>
  <td>Preferred Language</td>
  <td>JavaScript</td>
 </tr>
</table>

## Description

How can I remove items from a Kendo UI DropDownList?

## Solution

The following example demonstrates how to achieve the desired scenario.



```dojo
  <div id="example">
    <div id="cap-view" class="demo-section k-header">
      <h2>Customize your Kendo Cap</h2>
      <div id="cap" class="black-cap"></div>
      <div id="options">

        <input id="color" />
        <button class="k-button" id="remove">Remove items</button>
      </div>
    </div>
    <style scoped>
      .demo-section {
        width: 460px;
        height: 300px;
      }
      .demo-section h2 {
        text-transform: uppercase;
        font-size: 1em;
        margin-bottom: 30px;
      }
      #cap {
        float: left;
        width: 242px;
        height: 225px;
        margin: 20px 30px 30px 0;
        background-image: url('../content/web/dropdownlist/cap.png');
        background-repeat: no-repeat;
        background-color: transparent;
      }
      .black-cap {
        background-position: 0 0;
      }
      .grey-cap {
        background-position: 0 -225px;
      }
      .orange-cap {
        background-position: 0 -450px;
      }
      #options {
        padding: 1px 0 30px 30px;
      }
      #options h3 {
        font-size: 1em;
        font-weight: bold;
        margin: 25px 0 8px 0;
      }
      #get {
        margin-top: 25px;
      }
    </style>

    <script>
      $(document).ready(function() {
        var data = [
          { text: "Black", value: "1" },
          { text: "Orange", value: "2" },
          { text: "Grey", value: "3" }
        ];

        // create DropDownList from input HTML element
        $("#color").kendoDropDownList({
          dataTextField: "text",
          dataValueField: "value",
          dataSource: data
        });

        $("#remove").click(function() {
          var ddl =  $("#color").data("kendoDropDownList");

          var oldData = ddl.dataSource.data();

          ddl.dataSource.remove(oldData[0]); //remove first item
          ddl.dataSource.remove(oldData[oldData.length - 1]); //remove last item
        });
      });
    </script>
  </div>
```

## See Also

* [JavaScript API Reference of the DropDownList](/api/javascript/ui/dropdownlist)
* [How to Automatically Adjust the Width of a DropDownList]({% slug howto_automatically_adjust_width_dropdownlist %})
* [How to Create DropDownLists with Long Items]({% slug howto_create_listswith_long_items_dropdownlist %})
* [How to Detect Wrapper Focus Events]({% slug howto_detect_wrapper_focus_events_dropdownlist %})
* [How to Move the Group Label on Top of Items]({% slug howto_move_group_label_ontopof_items_dropdownlist %})
* [How to Prevent Popup Closure on Scroll]({% slug howto_prevent_popup_closure_onscroll_dropdownlist %})
* [How to Set DataSource Dynamically]({% slug howto_set_datasource_dynamically_dropdownlist %})
* [How to Update MVVM Bound Models on Load]({% slug howto_update_mvvm_model_onload_dropdownlist %})
