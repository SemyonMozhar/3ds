---
title: "��������� boot9strap (2xrsa)" #
lang: ru
permalink: installing-boot9strap-2xrsa.html
sidebar:
  nav: "installing-boot9strap-2xrsa"
---

��� ������������� [magnet](https://en.wikipedia.org/wiki/Magnet_URI_scheme)-������ � ���� ����������� ��������� torrent-������, �������� [Deluge](http://dev.deluge-torrent.org/wiki/Download)
{: .notice--success}

#### <a name="what_need" />��� �����������

* ������ ������ [SafeB9SInstaller](https://github.com/d0k3/SafeB9SInstaller/releases/latest)
* ������ ������ [boot9strap](https://github.com/SciresM/boot9strap/releases/latest) *(����������� ������ boot9strap; ����, ��� �������� `dev`-)* *(����������� ������ boot9strap; ����, ��� �������� `dev`-)*
* Homebrew [Starter Kit](http://smealum.github.io/ninjhax2/starter.zip)

#### <a name="instructions" />����������

##### <a name="part1" />����� I - ���������������� ������

1. ��������� �������
1. �������� SD-����� � ���������
1. ���������� _����������_ ����� `starter` �� ������ `starter.zip` � ������ ����� SD-�����
1. �������� ����� `boot9strap` � ����� SD-�����
1. ���������� `boot9strap.firm` � `boot9strap.firm.sha` �� `.zip-������` boot9strap � ����� `/boot9strap/` � ����� SD-�����
1. ���������� `arm9.bin` � `arm11.bin` �� `.zip-������` SafeB9SInstaller � ������ SD-�����
1. �������� SD-����� ������� � �������
1. �������� �������

##### <a name="part2" />����� II - ������ SafeB9SInstaller

1. ��������� ������� �� ������� � ��������� �� ������:
  + `http://2xrsa.3ds.guide`
  + ���� �� ������ �������� Wi-Fi �� 2DS ��� New 3DS, ��� ����� �������, ������� ������� � �������� �������� ���������� �� ��������� ������, � ����� ����� �������� �������
  + ���� ���������� ������ "This service is not available in your region", ��������� ������ � ��������� ���������� (System Settings) �� ��������������� ����, ������� ��� ���������� ��� 2.1.0 CTRTransfer
  + ���� �� ������ ��������� ������������ �������� �� ������ �������� CTRTransfer ��� �� ������ �������� ������ � ���������� ����, ������� ����������� ������������� � ������������ ���� � ������ `attwifi` ��� ������
  + ��� ������������� ������ ������, ���������� � ������� [�������� � �� �������](troubleshooting#ts_browser)
1. ���� �������� ��������, ���������� SafeB9SInstaller

##### <a name="part3" />����� III - ��������� boot9strap

1. ��������� ��������� ���� �������� ������������
1. ��� ��������� �������, ������� ��������� ���������� ������ ��� ��������� boot9strap
1. ����� ���������� ��������, ������� (A) ��� ������������
1. ���� ������� ���������� � boot9strap, ����� ������������� ����������, ������ ��� ������������ ����� ��� ���

��������� �� ���������� �� ��� ���, ���� �� �� ��������� ���������� �� ��������� ��������; ��� ������, ��� � ������ ����
{: .notice--warning}

___

�������, ��� ������������ *New 3DS*, �������� CTRTransfer �������� 2.1.0 *������* [������������ ��������� ����� NAND](godmode9-usage#nand_restore) � ���������� ����� ����������� "����� II - ��������� Luma3DS" � "����� III - ���������� �������" ������� [���������� ���������](finalizing-setup).
{: .notice--danger}

��������� ���: [���������� ���������](finalizing-setup)
{: .notice--success}

<div id="vk_comments"></div>
<script type="text/javascript">
VK.Widgets.Comments("vk_comments", {limit: 10, attach: "*"});
</script>