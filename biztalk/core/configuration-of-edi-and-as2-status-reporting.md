---
title: "構成の EDI および AS2 状態レポート |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 0c7fa76d-0d03-4b74-9a3a-60f4bd0534ff
caps.latest.revision: "15"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 051a03b735f3714910b415d5418ff84089c57940
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="configuration-of-edi-and-as2-status-reporting"></a>EDI および AS2 状態レポートの構成
ここでは、EDI および AS2 状態レポートの有効化、EDI、バッチ処理、および AS2 の各状態レポートに対する状態レポート フィルターと表示列の構成について説明します。  
  
## <a name="enabling-status-reporting"></a>状態レポートの有効化  
 EDI サブシステムおよび BAM サブシステムを搭載した [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] がサーバーにインストールされている場合のみ、そのサーバーで EDI 状態レポートを使用できます。 BAM インフラストラクチャがインストールされていない場合は、EDI/AS2 状態レポートを有効にできません。 また、サーバーが EDI 状態レポート データ ストアにアクセスできるように、サーバーは [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] グループのメンバーである必要もあります。  
  
 場合にその EDI メッセージ エントリが、パーティのインターチェンジの状態レポート UI に入力した、**レポートをオンに**でプロパティが選択されている、**全般プロパティ**のページ、**全般**  タブで、**アグリーメントのプロパティ** ダイアログ ボックス。 されているかを送信するパーティのインターチェンジが決定されない送信する場合と、場合にのみ、それらのインターチェンジの EDI メッセージ エントリを入力、 **EDI のアクティブ化レポート**X12 と EDIFACT の両方に対するフォールバック アグリーメントのプロパティが選択されています。 これは、EDI インターチェンジおよび関連する ACK の状態レポートに適用されます。 アグリーメントが特定された場合にのみ、バッチ状態レポートが有効になっていると、**レポートをオンに**でプロパティが選択されている**全般プロパティ**のページ、**全般**タブで、**アグリーメントのプロパティ** ダイアログ ボックス。  
  
 場合にそのトランザクション セットが、追跡データベースに格納された、 **reporting 用メッセージ ペイロードを格納**でプロパティが選択されている**全般プロパティ**のページ、**全般**タブで、**アグリーメントのプロパティ** ダイアログ ボックスまたは**レポート用にトランザクション セット/ペイロードを格納**プロパティは、フォールバック アグリーメントのプロパティで設定します。 このプロパティが選択されている場合のみ、トランザクション セットの詳細およびメッセージ コンテンツ状態レポートを使用できます。  
  
 場合にその AS2 メッセージ エントリが状態レポート UI に入力した、**レポートをオンに**でプロパティが選択されている、**全般プロパティ**のページ、**全般** タブ**アグリーメントのプロパティ** ダイアログ ボックス。 AS2 メッセージまたは Mdn を否認不可データベースに保存するで適切なプロパティを選択する必要があります、**送信者否認**または**受信者否認**一方向の AS2 アグリーメントのページタブで、**アグリーメントのプロパティ** ダイアログ ボックス。 これらのプロパティにより、AS2 メッセージおよび関連する MDN の状態レポートが有効になります。  
  
 信頼できるメッセージングの状態レポートが使用できる場合、 **MDN を受信しない場合は再送信 AS2 メッセージ**でプロパティが有効になっている**送信者の MDN 設定**の一方向のAS2アグリーメントタブのページ**アグリーメントのプロパティ** ダイアログ ボックス。  
  
 状態レポートを有効にする方法の詳細については、次を参照してください。[を有効にする EDI および AS2 状態レポート](../core/enabling-edi-and-as2-status-reports.md)です。  
  
## <a name="status-report-filters-and-display-columns"></a>状態レポートのフィルターと表示列  
 EDI および AS2 状態レポートにより、状態レポート用に保存されるデータの範囲をカスタマイズできます。 そのために操作を行う、**グループ ハブ**のページ、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールです。 状態レポートの状態レポート ペインを表示した後、レポートに表示するデータの範囲を選択できます。 そのためには、状態レポートのクエリ式に含めるフィルター値を選択します。  
  
 状態レポートに表示するデータの種類をカスタマイズすることもできます。  
  
> [!NOTE]
>  状態レポートが有効になっている場合、常にすべての状態がストレージに保存されます。 クエリ式または状態列をカスタマイズすることで、表示する保存データを定義します。  
  
 詳細については、次を参照してください。 [EDI および AS2 状態レポートを構成する](../core/configuring-an-edi-and-as2-status-report.md)です。  
  
## <a name="see-also"></a>参照  
 [EDI および AS2 状態レポート](../core/edi-and-as2-status-reporting.md)   
 [EDI インターチェンジし、関連する ACK の状態レポート](../core/edi-interchange-and-correlated-ack-status-report.md)   
 [バッチの状態レポート](../core/batch-status-report.md)   
 [インターチェンジの集計レポート](../core/interchange-aggregation-report.md)   
 [トランザクション セットの集計レポート](../core/transaction-set-aggregation-report.md)   
 [AS2 メッセージおよび関連する MDN 状態レポート](../core/as2-message-and-correlated-mdn-status-report.md)