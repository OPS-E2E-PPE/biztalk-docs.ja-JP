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
ms.openlocfilehash: 6bf0f3f5b5e6c50a02451215f56dbc3ec4c2939a
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65350580"
---
# <a name="edi-and-as2-status-reporting"></a>EDI および AS2 状態レポート
EDI 状態レポートを有効に運用担当者の EDI および AS2 の送信の状態を追跡します。 有効な場合、状態レポートは、インターチェンジには、インターチェンジに関連付けられたすべての確認など、ドキュメント交換トランザクションの包括的な状態を提供します。 これらのレポートは、受信、検証、バッチ処理、および EDI および AS2 メッセージの受信確認処理でデータを提供します。  
  
 これらのレポートを使用すると、保留中の状態と未確認のインターチェンジ、完全なインターチェンジ、エラーのシナリオまたはビジネス シナリオを取得します。 これらのレポートには、次の操作を行うことができます。  
  
- インターチェンジの受信を確認します。  
  
- 送信インターチェンジ待機確認を一覧します。  
  
- 受信したすべての拒否されたインターチェンジを一覧表示します。  
  
- 拒否された、または部分的に報告された送信インターチェンジの一覧が受け入れられます。  
  
  状態レポートに含まれるデータは、インターチェンジ制御セグメント ISA、TA1、GS、UNB、UNG など (機能確認状態) を除くから取得されます。  
  
  **状態レポートの UI**  
  
  EDI および AS2 状態レポートはから利用可能な[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソール。 **グループ ハブ**のページ、 **BizTalk グループ**ノード、EDI インターチェンジと関連する受信確認状態、バッチの状態と AS2 メッセージおよび関連する MDN の状態へのリンクがあります。 各レポートを含めるかが必要とする状態レポートを構築できるように、クエリ式から除外する状態パラメーターの範囲を提供します。  
  
  EDI インターチェンジの状態を表示することに加えて、インターチェンジのトランザクション セットを表示することもできます。 追跡 (BizTalkDTADb) データベースの EDI テーブルにメッセージ ペイロードのストレージを有効にするとこれを行います。 状態レポート UI の詳細を表示するコマンドを使用して、トランザクション セットを表示できます。  
  
  否認不可データベースに受信または送信 AS2 メッセージまたは Mdn を格納することもできます。 トランザクション セットまたは AS2 メッセージを表示するには、状態レポートにメッセージを右クリックし、適切なコマンドを選択します。  
  
  **状態レポートのコンポーネント**  
  
  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]状態レポートに関連するコンポーネントが次に示します。  
  
- EDI 逆アセンブラーで EDI 受信パイプラインを作成し、受信したインターチェンジについて、データ ストアに状態エントリを更新します。  
  
- EDI アセンブラーは EDI 送信パイプラインを作成して、送信インターチェンジのデータ ストアに状態エントリを更新します。  
  
- 状態レポート エントリを格納するデータ ストア。 これらは、データと EDI トランザクション セットおよび AS2 メッセージの内容を BizTalk 追跡データベース (BizTalkDTADb) の EDI メッセージ コンテンツ テーブルを追跡するため、BAM プライマリ インポート データベース  
  
- 状態レポート UI、**グループ ハブ**のページ、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、状態レポート データを表示するために使用  
  
- アグリーメント プロパティ オプションおよびフォールバック アグリーメント プロパティ オプション[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、有効にして、状態レポートを構成するために使用  
  
- BAM インフラストラクチャを利用する DTA および SQL 分析サーバー。  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [EDI および AS2 状態レポートの構成](../core/configuration-of-edi-and-as2-status-reporting.md)  
  
-   [EDI および AS2 状態レポートの種類](../core/types-of-edi-and-as2-status-reports.md)  
  
-   [EDI および AS2 状態レポート用に格納されるデータ](../core/data-stored-for-edi-and-as2-status-reports.md)  
  
-   [EDI および AS2 状態レポートのデータ格納方法](../core/how-data-is-stored-for-edi-and-as2-status-reports.md)