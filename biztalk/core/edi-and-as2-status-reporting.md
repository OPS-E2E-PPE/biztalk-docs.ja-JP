---
title: EDI および AS2 状態レポート |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a9e58b29-9be0-41d6-ad35-1aae28e1a784
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8a109398f4b3bff99ce7f45493839df6c3e5320f
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36993139"
---
# <a name="edi-and-as2-status-reporting"></a>EDI および AS2 状態レポート
EDI 状態レポートを使用すると、運用担当者は EDI および AS2 送信の状態を追跡できます。 状態レポートを有効にすると、インターチェンジおよび、それに関連付けられた受信確認を含むドキュメント交換トランザクションの総合的な状態が提供されます。 このレポートでは、EDI および AS2 メッセージの受信、検証、バッチ処理、受信確認処理に関するデータが提供されます。  
  
 このレポートを使用して、保留および未確認のインターチェンジ、完全なインターチェンジ、エラー シナリオ、またはビジネス シナリオの状態を取得できます。 このレポートを使用して、次の操作を実行できます。  
  
- インターチェンジの受信の確認  
  
- 送信インターチェンジ待機確認の一覧表示  
  
- 受信したすべての拒否インターチェンジの一覧表示  
  
- 拒否または一部受理としてレポートされた送信インターチェンジの一覧表示  
  
  状態レポートに含まれるデータは、ISA、TA1、GS、UNB、UNG (機能確認状態を除く) などのインターチェンジ制御セグメントから取得できます。  
  
  **状態レポートの UI**  
  
  EDI および AS2 状態レポートは、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理コンソールから使用できます。 **グループ ハブ**のページ、 **BizTalk グループ**ノード、EDI インターチェンジと関連する受信確認状態、バッチの状態と AS2 メッセージおよび関連する MDN の状態へのリンクがあります。 これらのレポートはそれぞれ、クエリ式に含める、またはクエリ式から除外する状態パラメーターの範囲を提供し、必要な状態レポートの構築を可能にします。  
  
  EDI インターチェンジの状態を表示するだけでなく、インターチェンジのトランザクション セットも表示できます。 これは、追跡 (BizTalkDTADb) データベースの EDI テーブルへのメッセージ ペイロードの格納を有効にすることによって実行できます。 状態レポート UI の詳細表示コマンドを使用して、トランザクション セットを表示できます。  
  
  受信または送信 AS2 メッセージ、または MDN を否認不可データベースに保存することもできます。 状態レポートのメッセージを右クリックし、適切なコマンドを選択することにより、トランザクション セットまたは AS2 メッセージを表示できます。  
  
  **状態レポートのコンポーネント**  
  
  状態レポートに関連する [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] コンポーネントは、次のとおりです。  
  
- 受信インターチェンジのデータ ストアに状態エントリを作成および更新する EDI 受信パイプラインの EDI 逆アセンブラー。  
  
- 送信インターチェンジのデータ ストアに状態エントリを作成および更新する EDI 送信パイプラインの EDI アセンブラー。  
  
- 状態レポート エントリを格納するデータ ストア。 これは、データ追跡用の BAM プライマリ インポート データベースと、EDI トランザクション セットおよび AS2 メッセージ コンテンツ用の BizTalk 追跡データベース (BizTalkDTADb) の EDI メッセージ コンテンツ テーブルです。  
  
- 状態レポート UI、**グループ ハブ**のページ、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、状態レポート データを表示するために使用  
  
- 状態レポートの有効化および構成に使用される [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理コンソールのアグリーメント プロパティ オプションおよびフォールバック アグリーメント プロパティ オプション。  
  
- BAM インフラストラクチャを利用する DTA および SQL 分析サーバー。  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [EDI および AS2 状態レポートの構成](../core/configuration-of-edi-and-as2-status-reporting.md)  
  
-   [EDI および AS2 状態レポートの種類](../core/types-of-edi-and-as2-status-reports.md)  
  
-   [EDI および AS2 状態レポート用に格納されるデータ](../core/data-stored-for-edi-and-as2-status-reports.md)  
  
-   [EDI および AS2 状態レポートのデータ格納方法](../core/how-data-is-stored-for-edi-and-as2-status-reports.md)