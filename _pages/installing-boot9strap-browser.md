---
title: "��������� boot9strap (�������)" #
lang: ru
permalink: installing-boot9strap-browser.html
sidebar:
  nav: "installing-boot9strap-browser"

---

���� �� ���������� ���� ���������� ����� � � ��� ����������� ��������� �������� �� ������ EmuNAND, �������, ��� ������ ����������� �������� ������ � SysNAND � �� ������ ��������� ��� ���� �������� � SysNAND. �������, ��� RedNAND � EmuNAND - ������� ������ ���������� [������ � ���� ��](http://3dbrew.org/wiki/NAND_Redirection) (����.).
{: .notice--info}

��� ������������� [magnet](https://en.wikipedia.org/wiki/Magnet_URI_scheme)-������ � ���� ����������� ��������� torrent-������, �������� [Deluge](http://dev.deluge-torrent.org/wiki/Download)
{: .notice--success}

#### <a name="what_need" />��� �����������

* ������ ������ [SafeB9SInstaller](https://github.com/d0k3/SafeB9SInstaller/releases/latest)
* ������ ������ [boot9strap](https://github.com/SciresM/boot9strap/releases/latest) *(����������� ������ boot9strap; ����, ��� �������� `dev`-)*
* Homebrew [Starter Kit](http://smealum.github.io/ninjhax2/starter.zip)

#### <a name="instructions" />����������

##### <a name="part1" />����� I - ���������������� ������

1. ��������� �������
1. �������� SD-����� � ���������
1. ���������� _����������_ ����� `starter` �� ������ `starter.zip` � ������ ����� SD-�����
1. �������� ����� `boot9strap` � ����� SD-�����
1. ���������� `boot9strap.firm` � `boot9strap.firm.sha` �� `.zip-������`boot9strap � ����� `/boot9strap/` � ����� SD-�����
1. ���������� `SafeB9SInstaller.dat` � `Launcher.dat` �� `.zip-������` SafeB9SInstaller � ������ SD-�����
1. �������� SD-����� ������� � �������
1. �������� �������

##### <a name="part2" />����� II - ������ SafeB9SInstaller

1. ��������� ������� �� ������� � ��������� �� ����� �� ��������� ������
  + `https://goo.gl/Pk5IZs` ��� `https://dukesrg.github.io/?SafeB9SInstaller.dat`
  + `https://goo.gl/f8GbSf` ��� `http://go.gateway-3ds.com/`
  + `https://goo.gl/ASCLSV` ��� `http://www.reboot.ms/3ds/load.html?Launcher.dat`
  + `https://goo.gl/etmY59` ��� `http://dukesrg.dynu.net/3ds/rop?GW17567.dat&Launcher.dat`
  + **��� ������������ ������� QR, ���� QR-������ ���� � ����� ������ ��������:**

	��� ����, ����� ������� � QR-scanner, ������� ������������ (L)+(R), �������� �� �������� ������, � ����� ������� ����������� � ������������ QR-���� �� ������ ������.
	{: .notice--info}

	![]({{ base_path }}/images/QR/dukeGithub.png)	![]({{ base_path }}/images/QR/gateway.png)
	<br>
	![]({{ base_path }}/images/QR/goReboot.png)	![]({{ base_path }}/images/QR/dukeDynu.png)
	{: .text-center}
    {: .notice--info}
  
  + � ������, ���� ������ ������ �� ���������, ���������� ��� ��������� (��������� ������� �� ����� ������������ ������ ������, � �� ����� ��� ������ �� ����� ������������ ��������� ���)
  + ��� ������������� ������, ���������� � ������� [�������� � �� �������](troubleshooting#ts_browser)
1. ���� �������� ��������, ���������� SafeB9SInstaller

##### <a name="part3" />����� III - ��������� boot9strap

1. ��������� ��������� ���� �������� �������������
1. ��� ��������� �������, ������� ��������� ���������� ������ ��� ��������� boot9strap
1. ����� ���������� ��������, ������� (A) ��� ������������
1. ���� ������� ���������� � boot9strap, ����� ������������� ����������, ��������� ������������ ����� ��� ���

��������� �� ���������� �� ��� ���, ���� �� �� ��������� ���������� �� ��������� ��������; ��� ������, ��� � ������ ����
{: .notice--warning}
 
___

��������� ���: [���������� ���������](finalizing-setup)
{: .notice--success}

<div id="vk_comments"></div>
<script type="text/javascript">
VK.Widgets.Comments("vk_comments", {limit: 10, attach: "*"});
</script>