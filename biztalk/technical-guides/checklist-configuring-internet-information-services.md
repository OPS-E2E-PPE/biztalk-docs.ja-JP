---
title: 'チェックリスト: インターネット インフォメーション サービスの構成 |Microsoft ドキュメント'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 186f82c0-bd50-4c79-a403-8b0d91cc68d6
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 24c2c0c97cb70dca268273d9ed5855f72372a2ca
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
ms.locfileid: "25976504"
---
# <a name="checklist-configuring-internet-information-services"></a>チェックリスト: インターネット インフォメーション サービスを構成します。
このトピックは、実稼働環境で使用するインターネット インフォメーション サービス (IIS) を準備するときに従う必要がありますの手順を一覧表示[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]環境。  
  
|手順|リファレンス|  
|-----------|---------------|  
|発行するよう IIS を設定[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]Web サービスと WCF サービス|-参照[「Web サービスを有効にする」](http://go.microsoft.com/fwlink/?LinkId=153335) (http://go.microsoft.com/fwlink/?LinkId=153335)、BizTalk Server のドキュメントにします。<br />-参照[「を構成する IIS の分離 WCF 受信アダプタ」](http://go.microsoft.com/fwlink/?LinkId=202825)(http://go.microsoft.com/fwlink/?LinkId=202825)、BizTalk Server のドキュメントにします。|  
|いることを確認[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]Web サービスと WCF サービスが正しく動作します。|-参照[「公開 Web サービスのテスト」](http://go.microsoft.com/fwlink/?LinkId=153336) (http://go.microsoft.com/fwlink/?LinkId=153336)、BizTalk Server のドキュメントにします。<br />-参照[「方法に作成、.NET アプリケーションをテスト、WCF サービス発行と、BizTalk WCF サービス公開ウィザード」](http://go.microsoft.com/fwlink/?LinkId=202830) (http://go.microsoft.com/fwlink/?LinkId=202830)、BizTalk Server のドキュメントにします。|  
|ロック ダウン[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]Web サービス。<br /><br /> -Web.config または machine.config ファイルでデバッグ スイッチをオフにします。<br />-POST が許可された唯一の動詞になるように構成します。|-Microsoft サポート技術情報の記事 815145 を参照して["する方法: ASP.NET Web アプリケーションのロックダウンまたは Web サービス"](http://go.microsoft.com/fwlink/?LinkId=153337) (http://go.microsoft.com/fwlink/?LinkId=153337)。<br />-参照[「ASP.NET 編集ルール ダイアログ ボックス」](http://go.microsoft.com/fwlink/?LinkID=64566) (http://go.microsoft.com/fwlink/?LinkID=64566)、.NET Framework 2.0 マニュアルを参照します。|  
|BizTalk Server Web サービスと WCF サービスの間で負荷を分散する NLB (またはその他のロード バランサー) を使用して、負荷分散を構成します。|-   **Windows Server 2008 の**: を参照してください[「ネットワーク負荷分散展開ガイド」](http://go.microsoft.com/fwlink/?LinkId=153139) (http://go.microsoft.com/fwlink/?LinkId=153139)。<br />-   **Windows Server 2003 の**: を参照してください["ネットワーク負荷分散: Windows 2000 および Windows Server 2003 の構成のベスト プラクティス"](http://go.microsoft.com/fwlink/?LinkID=69529) (http://go.microsoft.com/fwlink/?LinkID=69529)。|  
|Web サービスをチューニングするためには、IIS と ASP.NET の設定を変更します。 **注:** ASP.NET 2.0 では、自動調整が含まれています、ためこれらの設定を変更する必要はありませんで自動構成が有効な ASP.NET 2.0 Web サイトの web.config ファイルの\<processModel\>セクションです。 "autoConfig = true"既定の設定です。|設定を確認して、"ASP.NET HTTP または SOAP アダプターのパフォーマンスに影響する"」の「 [「構成パラメーターをに影響するアダプターのパフォーマンス」](http://go.microsoft.com/fwlink/?LinkId=153338) (http://go.microsoft.com/fwlink/?LinkId=153338)、BizTalk Server のドキュメントにします。|  
|発行のための方法を実装する[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]Web サービスと WCF サービスです。|-参照[インターネットに接続された Web サービスと WCF サービスを発行](../technical-guides/publishing-internet-facing-web-services-and-wcf-services.md)です。<br />-参照[「WCF サービスの公開」](http://go.microsoft.com/fwlink/?LinkId=202827) (http://go.microsoft.com/fwlink/?LinkId=202827)、BizTalk Server のドキュメントにします。|  
|IIS のパフォーマンスを最適化するためのベスト プラクティスに従います。|参照してください[「IIS のパフォーマンスをポンプする方法は 10 の上位」](http://go.microsoft.com/fwlink/?LinkId=109107) (http://go.microsoft.com/fwlink/?LinkId=109107)。|  
|高パフォーマンスの IIS の web アプリケーションを記述するためのベスト プラクティスに従います。|参照してください["高パフォーマンスを記述するための 10 のヒントは、アプリケーションを Web"](http://go.microsoft.com/fwlink/?LinkId=98290) (http://go.microsoft.com/fwlink/?LinkId=98290)。|  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [インターネットに接続された Web サービスと WCF サービスの公開](../technical-guides/publishing-internet-facing-web-services-and-wcf-services.md)