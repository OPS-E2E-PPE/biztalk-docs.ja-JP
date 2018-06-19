---
title: AppFabric をインストールするサービスの接続 |Microsoft ドキュメント
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
ms.openlocfilehash: b3d10862a6a60d173cc68c25d0dcc463d2f16e38
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22298690"
---
# <a name="installing-appfabric-connect-for-services"></a>サービスの接続 AppFabric をインストールします。
このガイドでは、BizTalk Server 2010 Feature Pack (2010 年 10 月) をインストールする方法について説明します。 Feature pack の機能強化を提供するサービスの機能用の BizTalk Server 2010 AppFabric Connect のインストール、 **BizTalk WCF サービス公開ウィザード**と**WCF アダプター サービス開発ウィザード**. Feature pack をインストールした後は、BizTalk Server アイテム、内部設置型の範囲を拡張または LOB アプリケーションを Windows Azure AppFabric Service Bus エンドポイントを追加することによってクラウドことができます。  
  
## <a name="prerequisites"></a>前提条件  
 BizTalk Server 2010 Feature Pack は、BizTalk WCF サービス公開ウィザードと WCF アダプター サービス開発ウィザードに拡張機能を提供します。 BizTalk WCF サービス公開ウィザードは BizTalk Server 2010 の開発ツールで使用できますが、WCF アダプター サービス開発ウィザードは BizTalk Adapter Pack 2010 で使用可能です。 そのため、この feature pack をインストールする前に、BizTalk Server 2010 の開発ツールまたは BizTalk Adapter Pack 2010 のいずれかまたはその両方をインストールが必要です。 これらのインストール済みの 1 つだけある場合は、親製品のインストールに関連するウィザードのみは機能パックのインストールの一部として更新されます。  
  
 また、これらのウィザードを使用するためのいくつかの前提条件があります。 各ウィザードの前提条件の完全な一覧は、ウィザードを使用する方法を説明するトピックに表示されます。 トピックへのリンクがで提供される[を使用してサービスの接続の AppFabric](../technical-guides/installing-appfabric-connect-for-services.md#BKMK_Using)です。  
  
## <a name="installing-biztalk-server-2010-feature-pack"></a>BizTalk Server 2010 Feature Pack をインストールします。  
 AppFabric 接続サービスをインストールする次の手順を実行します。  
  
#### <a name="to-install-the-feature-pack"></a>Feature pack をインストールするには  
  
1.  ダウンロードからインストール可能なサービスの AppFabric Connect [http://go.microsoft.com/fwlink/?LinkId=204701](http://go.microsoft.com/fwlink/?LinkId=204701)です。 機能パック インストーラーを起動する、自己解凍 BizTalkServer2010_FeaturePack.exe ファイルを実行します。  
  
2.  **ようこそ** ページで、をクリックして**次**です。  
  
3.  ライセンス条項に同意し、をクリックして**次**し、次の画面でクリック **[次へ]** もう一度です。  
  
4.  クリックして、ウィザードでは、機能パックのインストールが完了したら、**完了**です。  
  
##  <a name="BKMK_Using"></a>AppFabric を使用してサービスの接続  
 AppFabric 接続サービスをインストールした後に、次の操作を行うことができます。  
  
-   使用して、 **BizTalk WCF サービス公開ウィザード**Azure AppFabric Service Bus のリレー エンドポイントを使用して WCF サービスとしての BizTalk アイテム (オーケストレーション、スキーマなど) を公開します。 詳細については、次を参照してください。 [http://go.microsoft.com/fwlink/?LinkId=204700](http://go.microsoft.com/fwlink/?LinkId=204700)です。  
  
-   使用して、 **WCF アダプター サービス開発ウィザード**Azure AppFabric Service Bus のリレー エンドポイントを使用して WCF サービスとしての LOB アプリケーションでの操作を公開します。 詳細については、次を参照してください。 [http://go.microsoft.com/fwlink/?LinkId=204699](http://go.microsoft.com/fwlink/?LinkId=204699)です。  
  
## <a name="uninstalling-biztalk-server-2010-feature-pack"></a>BizTalk Server 2010 Feature Pack をアンインストールします。  
 このセクションでは、AppFabric 接続サービスのアンインストールについてを説明します。  
  
#### <a name="to-uninstall-the-feature-pack"></a>機能パックをアンインストールするには  
  
1.  Windows Update を開き、**更新履歴の表示**、クリックして**インストールされた更新プログラム**です。  
  
2.  インストールされている更新プログラムの一覧から  **BizTalk Server 2010**カテゴリを右クリックして**BizTalk Server 2010 Feature Pack (2010 年 10 月) LDR**、し、**アンインストール**. この機能パックをアンインストールするかどうかを確認する ダイアログ ボックスでをクリックして**はい**です。  
  
3.  Feature pack をアンインストールするかどうかを確認するリストを更新します。  
  
## <a name="copyright"></a>著作権  
 このドキュメントはプレリリースのソフトウェア製品を対象にしており、最終製品のリリース前に大幅に変更される可能性があります。  このドキュメントは参考情報としてのみ提供されるものであり、Microsoft はこのドキュメントの内容について、明示か黙示かを問わず、一切保証しません。  このドキュメントに記載されている情報 (URL 等のインターネット Web サイトに関する情報を含む) は、将来予告なしに変更されることがあります。  このドキュメントの使用またはその結果に対するリスクは、すべてお客様が負うものとします。  特に記載のない限り、例として使用される企業、組織、製品、ドメイン名、電子メール アドレス、ロゴ、人物、場所、およびイベントはすべて架空のものです。  実在する企業、組織、製品、ドメイン名、電子メール アドレス、ロゴ、人物、場所、イベントとは一切関係ありません。  お客様ご自身の責任において、適用されるすべての著作権関連法規に従ったご使用を願います。  このソフトウェアおよびマニュアルのいかなる部分も、米国 Microsoft Corporation の書面による許諾を受けることなく、その目的を問わず、どのような形態であっても、複製または譲渡することは禁じられています。ここでいう形態とは、複写や記録など、電子的な、または物理的なすべての手段を含みます。  
  
 Microsoft は、このマニュアルに記載されている内容に関し、特許、特許申請、商標、著作権、またはその他の無体財産権を有する場合があります。  別途マイクロソフトのライセンス契約上に明示の規定がない限り、このドキュメントはこれらの特許、商標、著作権、またはその他の無体財産権に関する権利をお客様に許諾するものではありません。  
  
 © 2010 Microsoft Corporation.  All rights reserved.  
  
 Microsoft、Active Directory、ActiveX、BizTalk、Excel、InfoPath、JScript、IntelliSense、Internet Explorer、MSDN、Outlook、PivotChart、PivotTable、PowerPoint、SharePoint、Tahoma、Visio、Visual Basic、Visual C++、Visual C#、Visual SourceSafe、Visual Studio、Win32、Windows、Windows NT、Windows PowerShell、Windows Server、Windows Server System は、Microsoft グループ企業各社の商標です。  
  
 記載されている SAP、R/3、mySAP、mySAP.com、xApps、xApp、SAP NetWeaver、その他の SAP 製品とサービス、およびそれらの各ロゴは、SAP AG のドイツおよびその他の国における商標または登録商標です。 記載されているその他すべての製品名およびサービス名は、各社の商標です。 このドキュメントに含まれているデータは、情報提供のみを目的としています。 各国固有の製品仕様は異なる場合があります。  
  
 記載されている会社名、製品名には、各社の商標のものもあります。