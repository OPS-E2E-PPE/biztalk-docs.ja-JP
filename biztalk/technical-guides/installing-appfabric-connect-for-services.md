---
title: AppFabric Connect サービスのインストール |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 1de3bf49-e3cc-4d3f-9883-9a2c472f3647
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2f140177ec2342bfb30d9efecc0e099894714fa0
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65400190"
---
# <a name="installing-appfabric-connect-for-services"></a>AppFabric Connect サービスのインストール
このガイドは、BizTalk Server 2010 Feature Pack (2010 年 10 月) をインストールする方法について説明します。 Feature pack の機能強化を提供するサービス機能用の BizTalk Server 2010 の AppFabric Connect のインストール、 **BizTalk WCF サービス公開ウィザード**、 **WCF アダプター サービス開発ウィザード**. Feature pack をインストールした後は、BizTalk Server のアイテムで、オンプレミスのリーチを拡張または LOB アプリケーションをクラウドで Windows Azure AppFabric Service Bus エンドポイントを追加できるようができます。  
  
## <a name="prerequisites"></a>前提条件  
 BizTalk Server 2010 Feature Pack は、BizTalk WCF サービス公開ウィザードと WCF アダプター サービス開発ウィザードを拡張機能を提供します。 BizTalk WCF サービス公開ウィザードは BizTalk Server 2010 の開発ツールで使用できますが、WCF アダプター サービス開発ウィザードは BizTalk Adapter Pack 2010 で使用できます。 そのため、feature pack をインストールする前に、BizTalk Server 2010 の開発ツールまたは BizTalk Adapter Pack 2010 またはその両方をインストールが必要です。 これらのインストール済みの 1 つだけある場合は、親製品のインストールに関連するウィザードのみは機能パックのインストールの一部として更新されます。  
  
 また、これらのウィザードを使用するためのいくつかの前提条件があります。 各ウィザードの前提条件の完全な一覧は、ウィザードを使用する方法を説明するトピックに表示されます。 トピックへのリンクが記載[サービスの AppFabric Connect を使用して](../technical-guides/installing-appfabric-connect-for-services.md#BKMK_Using)します。  
  
## <a name="installing-biztalk-server-2010-feature-pack"></a>BizTalk Server 2010 Feature Pack をインストールします。  
 サービスの AppFabric Connect をインストールするには、次の手順に従います。  
  
#### <a name="to-install-the-feature-pack"></a>Feature pack をインストールするには  
  
1.  ダウンロードからインストール可能なサービスの AppFabric Connect [ http://go.microsoft.com/fwlink/?LinkId=204701](http://go.microsoft.com/fwlink/?LinkId=204701)します。 機能パック インストーラーを起動する、自己解凍 BizTalkServer2010_FeaturePack.exe ファイルを実行します。  
  
2.  **へようこそ**  ページで **次**します。  
  
3.  ライセンス条項に同意し、 **[次へ]** し、次の画面でクリック **[次へ]** もう一度です。  
  
4.  ウィザードでは、機能パックのインストールが完了したら、クリックして**完了**します。  
  
##  <a name="BKMK_Using"></a> AppFabric を使用して、サービスの接続  
 サービスの AppFabric Connect をインストールした後に、次の操作を行うことができます。  
  
-   使用して、 **BizTalk WCF サービス公開ウィザード**BizTalk アイテム (オーケストレーション、スキーマなど) を Azure AppFabric Service Bus のリレー エンドポイントで WCF サービスとして公開します。 詳細については、次を参照してください。 [ http://go.microsoft.com/fwlink/?LinkId=204700](http://go.microsoft.com/fwlink/?LinkId=204700)します。  
  
-   使用して、 **WCF アダプター サービス開発ウィザード**LOB アプリケーションでの操作を Azure AppFabric Service Bus のリレー エンドポイントで WCF サービスとして公開します。 詳細については、次を参照してください。 [ http://go.microsoft.com/fwlink/?LinkId=204699](http://go.microsoft.com/fwlink/?LinkId=204699)します。  
  
## <a name="uninstalling-biztalk-server-2010-feature-pack"></a>BizTalk Server 2010 Feature Pack をアンインストールします。  
 このセクションでは、サービスの AppFabric Connect のアンインストールについてを説明します。  
  
#### <a name="to-uninstall-the-feature-pack"></a>機能パックをアンインストールするには  
  
1.  Windows の更新を開き、[**更新履歴の表示**、] をクリックし、**インストールされた更新プログラム**します。  
  
2.  インストール済みの更新の一覧から  **BizTalk Server 2010**カテゴリを右クリックして**BizTalk Server 2010 Feature Pack (October 2010) LDR**、し、**アンインストール**. Feature pack をアンインストールするかどうかを確認するダイアログ ボックス、**はい**します。  
  
3.  Feature pack をアンインストールするかどうかを確認するリストを更新します。  
  
## <a name="copyright"></a>著作権  
 このドキュメントでは、プレリリース版ソフトウェア製品より前の最終的な市販リリースに先立って大幅に変更される可能性がありますをサポートしています。  このドキュメントは情報目的のみで提供されており、Microsoft では、一切の保証、明示または黙示にかかわらず、このドキュメントではありません。  このドキュメントに記載されている情報 (URL 等のインターネット Web サイトに関する情報を含む) は、将来予告なしに変更されることがあります。  使用またはこのドキュメントの使用から結果全体のリスクは、ユーザーに残ります。  特に記載のない限り、例として使用される企業、組織、製品、ドメイン名、電子メール アドレス、ロゴ、人物、場所、およびイベントはすべて架空のものです。  実在する企業、組織、製品、ドメイン名、電子メール アドレス、ロゴ、人物、場所、イベントとは一切関係ありません。  お客様ご自身の責任において、適用されるすべての著作権関連法規に従ったご使用を願います。  このソフトウェアおよびマニュアルのいかなる部分も、米国 Microsoft Corporation の書面による許諾を受けることなく、その目的を問わず、どのような形態であっても、複製または譲渡することは禁じられています。ここでいう形態とは、複写や記録など、電子的な、または物理的なすべての手段を含みます。  
  
 Microsoft は、このマニュアルに記載されている内容に関し、特許、特許申請、商標、著作権、またはその他の無体財産権を有する場合があります。  別途マイクロソフトのライセンス契約上に明示の規定がない限り、このドキュメントはこれらの特許、商標、著作権、またはその他の無体財産権に関する権利をお客様に許諾するものではありません。  
  
 © 2010 Microsoft Corporation.  All rights reserved.  
  
 Microsoft、Active Directory、ActiveX、BizTalk、Excel、InfoPath、JScript、IntelliSense、Internet Explorer、MSDN、Outlook、ピボット グラフ、ピボット テーブル、PowerPoint、SharePoint、Tahoma、Visio、Visual Basic、Visual C++Visual、 C#、Visual SourceSafe、Visual Studio、Win32、Windows、Windows NT、Windows PowerShell、Windows Server、Windows Server System、および Windows Server は、Microsoft グループ企業の商標です。  
  
 SAP、R/3、mySAP、mySAP.com、xApps、xApp、SAP NetWeaver、およびその他の SAP 製品とサービスが記載されているだけでなくそれらの各ロゴ、商標 SAP AG のドイツおよび、世界中の他のいくつかの国における登録商標です。 その他の製品とサービス名説明はすべて、各社の商標です。 このドキュメントに含まれるデータは情報目的のみでは機能します。 各国語の製品仕様が異なる場合があります。  
  
 記載されている会社名、製品名には、各社の商標のものもあります。