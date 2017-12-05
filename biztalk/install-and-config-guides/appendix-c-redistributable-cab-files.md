---
title: "付録 c: 再配布可能 CAB ファイル |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c2049d61-e169-4b30-869a-33d5af097941
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a1a1f2b6866a2841abaa248479430a7584db3a0b
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
---
# <a name="appendix-c-redistributable-cab-files"></a>付録 C: 再配布可能な CAB ファイル
これらの CAB ファイルは BizTalk Server セットアップで利用されます。

## <a name="biztalk-2016-cab-files"></a>BizTalk 2016 CAB ファイル

|言語|ダウンロード リンク|  
|--------------|-------------------|  
|EN|<ul><li>**X64**<br /><br /> <ul><li>Windows Server 2016: [http://go.microsoft.com/fwlink/p/?LinkId=746413](http://go.microsoft.com/fwlink/p/?LinkId=746413)</li><li>Windows Server 2012 R2: [http://go.microsoft.com/fwlink/p/?LinkId=746412](http://go.microsoft.com/fwlink/p/?LinkId=746412)</li><li>Windows 10: [http://go.microsoft.com/fwlink/p/?LinkId=746408](http://go.microsoft.com/fwlink/p/?LinkId=746408)</li><li>Windows 8.1: [http://go.microsoft.com/fwlink/p/?LinkId=746411](http://go.microsoft.com/fwlink/p/?LinkId=746411)</li></ul></li><li>**X32**<br /><br /><ul><li>Windows 10: [http://go.microsoft.com/fwlink/p/?LinkId=746409](http://go.microsoft.com/fwlink/p/?LinkId=746409)</li><li>Windows 8.1: [http://go.microsoft.com/fwlink/p/?LinkId=746410](http://go.microsoft.com/fwlink/p/?LinkId=746410)</li></ul></li></ul>|  

> [!NOTE] 
> Windows 10 と Windows Server 2016 では、Windows 8.1 または Windows Server 2012 R2 と同じ CAB ファイルが利用されます。 結果として、ファイル名が同じになります。

## <a name="biztalk-2013-r2-and-2013-cab-files"></a>BizTalk 2013 R2 ファイルと 2013 CAB ファイル  
  
|言語|ダウンロード リンク|  
|--------------|-------------------|  
|EN|<ul><li>**X64**<br /><br /> <ul><li>Windows Server 2012: [http://go.microsoft.com/fwlink/p/?LinkId=269616](http://go.microsoft.com/fwlink/p/?LinkId=269616)</li><li>Windows Server 2008: [http://go.microsoft.com/fwlink/p/?LinkId=269613](http://go.microsoft.com/fwlink/p/?LinkId=269613)</li><li>Windows 8: [http://go.microsoft.com/fwlink/p/?LinkId=269615](http://go.microsoft.com/fwlink/p/?LinkId=269615)</li><li>Windows 7: [http://go.microsoft.com/fwlink/p/?LinkId=269614](http://go.microsoft.com/fwlink/p/?LinkId=269614)</li></ul></li><li>**X32**<br /><br /> <ul><li>Windows 8: [http://go.microsoft.com/fwlink/p/?LinkId=269612](http://go.microsoft.com/fwlink/p/?LinkId=269612)</li><li>Windows 7: [http://go.microsoft.com/fwlink/p/?LinkId=269611](http://go.microsoft.com/fwlink/p/?LinkId=269611)</li></ul></li></ul>|  
  
## <a name="important-info"></a>重要な情報

- SQL XML には、CAB ファイルに含まれていない独自のソフトウェア要件 (`.NET Framework 3.5` や `.NET Framework 2.0` など) がある場合があります。 BizTalk Server からインターネットにアクセスできる場合、SQL XML ソフトウェア要件は自動的にインストールされます。 BizTalk Server がインターネットにアクセスできない場合は、SQL XML ソフトウェア要件を手動でインストールします。

- CAB ファイルのインストール パスが記載されても、 **Setup.xml**インストール フォルダー内のファイル ([!INCLUDE[btsBizTalkServerPathx64_md](../includes/btsbiztalkserverpathx64-md.md)]\<バージョン\>)。
  
-   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] に必要なソフトウェアの一部は、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] のセットアップ実行時にコンピューターにインストールされます。  
  
-   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] のセットアップでは、前提条件のソフトウェアを Web からダウンロードするか、CAB ファイルから抽出するよう選択できます。 CAB ファイルを選択すると、セットアップの実行前に CAB ファイルをダウンロードします。  
  
-   旧バージョンの [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] の CAB ファイルを使用することはできません。 CAB ファイルは、表にあるリンクからダウンロードする必要があります。  
  
-   CAB ファイルを Telnet セッションでダウンロードすることはできません。  