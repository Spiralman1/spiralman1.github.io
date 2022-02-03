---
layout: default
---

Text can be **bold**, _italic_, or ~~strikethrough~~.

[Link to another page](./another-page.html).
[Link to another page](./another-page2.html).
[Link to another page](./another-page3.html).

What happens if I chag this.

There should be whitespace between paragraphs. We recommend including a README, or a file with information about your project.

# Header 1

This is a normal paragraph following a header. GitHub is a code hosting platform for version control and collaboration. It lets you and others work together on projects from anywhere.

## Header 2

> #create Virtual switch#

Get-NetAdapter
New-VMSwitch –Name “External VM Switch” –AllowManagement $True –NetAdapterName “Local Area Connection”
Get-VMSwitch
---------------------------------------

#create VM#

New-VM -Name server2019 -path C:\vm-machine -MemoryStartupBytes 8000MB

# New-VHD -Path c:\vm-Machine\Testmahcine\Testmachine.vhdx -SizeBytes 10GB -Dynamic 	#create new vhd
# Set-VMDvdDrive -server2019 -ControllerNumber 1 -Path					#map ISO image

				*OR*

Add-VMHardDiskDrive -VMName server2019 start vm-path "C:\hyperv\vhd\VHDfile.vhd" 		#use existing VHD

start-vm server2019

get-vm *

Get-VMNetworkAdapter -VMName Server2019

Get-VM "server2019" | Get-VMNetworkAdapter | Connect-VMNetworkAdapter -SwitchName "extenal switch name"		# assign virtual switch

get-vmswitch | select *

get-vm -n server2019 | Select -ExpandProperty NetWorkAdapters

#get-vm | ?{$_.State -eq "Running"} | select -ExpandProperty networkadapters | select vmname, macaddress, switchname, ipaddresses | ft -wrap -autosize						#View info for all VM adapters**


# Set-VMhost -EnableEnhancedSessionMode $True						#Enable Enhanced Session Mode 

# Enable-PSRemoting 									#enable remote management from hyperv gui

>
> When something is important enough, you do it even if the odds are not in your favor.

### Header 3

```js
// Javascript code with syntax highlighting.
var fun = function lang(l) {
  dateformat.i18n = require('./lang/' + l)
  return true;
}
```

```ruby
# Ruby code with syntax highlighting
GitHubPages::Dependencies.gems.each do |gem, version|
  s.add_dependency(gem, "= #{version}")
end
```

#### Header 4

*   This is an unordered list following a header.
*   This is an unordered list following a header.
*   This is an unordered list following a header.

##### Header 5

1.  This is an ordered list following a header.
2.  This is an ordered list following a header.
3.  This is an ordered list following a header.

###### Header 6

| head1        | head two          | three |
|:-------------|:------------------|:------|
| ok           | good swedish fish | nice  |
| out of stock | good and plenty   | nice  |
| ok           | good `oreos`      | hmm   |
| ok           | good `zoute` drop | yumm  |

### There's a horizontal rule below this.

* * *

### Here is an unordered list:

*   Item foo
*   Item bar
*   Item baz
*   Item zip

### And an ordered list:

1.  Item one
1.  Item two
1.  Item three
1.  Item four

### And a nested list:

- level 1 item
  - level 2 item
  - level 2 item
    - level 3 item
    - level 3 item
- level 1 item
  - level 2 item
  - level 2 item
  - level 2 item
- level 1 item
  - level 2 item
  - level 2 item
- level 1 item

### Small image

![Octocat](https://github.githubassets.com/images/icons/emoji/octocat.png)

### Large image

![Branching](https://guides.github.com/activities/hello-world/branching.png)


### Definition lists can be used with HTML syntax.

<dl>
<dt>Name</dt>
<dd>Godzilla</dd>
<dt>Born</dt>
<dd>1952</dd>
<dt>Birthplace</dt>
<dd>Japan</dd>
<dt>Color</dt>
<dd>Green</dd>
</dl>

```
Long, single-line code blocks should not wrap. They should horizontally scroll if they are too long. This line should be long enough to demonstrate this.
```

```
The final element.
```
