$Id$

Description:
Provides splitting up long Drupal content into sub pages by number of characters/words or by 
a placeholder HTML tag. Smart Paging feature can be applied only to CCK fields (with text format) 
of node, user and taxonomy term entities. URL for sub pages made more SEO friendly and works even 
for aliased URL path. The user has more control over Smart Paging configuration, each content has 
its own Smart Paging settings.

It splits complex HTML markup content more accurately:

<div class="text-important">
  <p class="info">
  Long content paragraph... 
<!--pagebreak-->
  Continuation of long content paragraph.
  </p>
  <ul class="text-note">
    <li>List #1</li>
    <li>Long list #2...
 <!--pagebreak-->
    Continuation of long list #2</li>
    <li>List #3</li>
  </ul>
</div>

...into this:

<div class="text-important">
  <p class="info">
  Long content paragraph... 
  </p>
</div>
------------Page 1------------
<div class="text-important">
  <p class="info">
  Continuation of long content paragraph.
  </p>
  <ul class="text-note">
    <li>List #1</li>
    <li>Long list #2...</li>
  </ul>
</div>
------------Page 2------------
<div class="text-important">
  <ul class="text-note">
    <li>Continuation of long list #2</li>
    <li>List #3</li>
  </ul>
</div>
------------Page 3------------

Requirements:
Drupal 7.x

Installation:
1. Copy the extracted smart_paging directory to your Drupal sites/all/modules directory.
2. Login as an administrator. Enable the module at the http://www.example.com/?q=admin/modules
3. Configure Smart Paging at http://www.example.com/?q=admin/config/content/smart_paging
4. Enable Smart Paging input filter at http://www.example.com/?q=admin/config/content/formats

Support:
Please use the issue queue for filing bugs with this module at
http://drupal.org/project/issues/smart_paging