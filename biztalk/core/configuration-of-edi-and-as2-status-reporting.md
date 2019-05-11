---
title: 構成の EDI および AS2 状態レポート |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0c7fa76d-0d03-4b74-9a3a-60f4bd0534ff
caps.latest.revision: 15
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7bf9108b2302097373f2930c8408fda13b787842
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65391495"
---
# <a name="configuration-of-edi-and-as2-status-reporting"></a>構成の EDI および AS2 状態レポート
このトピックでは、EDI および AS2 状態レポートの有効化について説明しますと状態の構成は、レポート フィルターと、edi、バッチ処理、列を表示および AS2 状態レポートします。  
  
## <a name="enabling-status-reporting"></a>状態レポートの有効化  
 EDI 状態レポートのみで利用できるサーバー場合[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]EDI および BAM サブシステムとそのサーバーにインストールされます。 BAM インフラストラクチャがインストールされていない場合、edi/as2 状態レポートを有効にすることはできません。 サーバーは、EDI 処理のメンバーでもある必要があります[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]EDI 状態レポートのデータ ストアにアクセス権があるようにグループ化します。  
  
 EDI メッセージ エントリが入力されます、状態レポート UI で、パーティのインターチェンジの場合、**レポートをオン**でプロパティが選択されている、**全般プロパティ**のページ、 **全般**  タブで、**アグリーメントのプロパティ** ダイアログ ボックス。 されているかを送信するパーティのインターチェンジが決定されない送信する場合と、場合にのみ、それらのインターチェンジの EDI メッセージ エントリを入力、 **EDI のアクティブ化レポート**X12 と EDIFACT の両方に対するフォールバック アグリーメントのプロパティが選択されています。 これは、EDI インターチェンジと関連する ACK の状態レポートに適用されます。 アグリーメントが特定された場合にのみ、バッチ状態レポートが有効になっていると、**レポートをオン**でプロパティが選択されている**全般プロパティ**のページ、**全般**タブで、**アグリーメントのプロパティ** ダイアログ ボックス。  
  
 トランザクション セットの場合、追跡データベースに格納されます、**メッセージ ペイロードを格納するレポートの**でプロパティが選択されている**全般プロパティ**のページ、**全般**タブで、**アグリーメントのプロパティ** ダイアログ ボックスまたは**レポート用にトランザクション セット/ペイロードを格納**フォールバック アグリーメント プロパティでプロパティを設定します。 トランザクション セットの詳細およびメッセージ コンテンツ状態レポートは、このプロパティが選択されている場合のみなります。  
  
 場合にその AS2 メッセージ エントリが、状態レポート UI で入力した、**レポートをオン**でプロパティが選択されている、**全般プロパティ**のページ、**全般** タブ**アグリーメントのプロパティ** ダイアログ ボックス。 AS2 メッセージまたは Mdn を否認不可データベースに保存するで適切なプロパティを選択する必要があります、**送信者否認**または**受信者否認**一方向の AS2 アグリーメントのページタブで、**アグリーメントのプロパティ** ダイアログ ボックス。 これらのプロパティは、AS2 メッセージおよび関連する MDN 状態レポートを有効にします。  
  
 信頼できるメッセージングの状態レポートが提供される場合、 **MDN を受信しない場合は再送信 AS2 メッセージ**でプロパティが有効になっている**送信者の MDN 設定**の一方向のAS2アグリーメントタブのページ**アグリーメントのプロパティ** ダイアログ ボックス。  
  
 状態レポートを有効にする方法の詳細については、次を参照してください。[を有効にする EDI および AS2 状態レポート](../core/enabling-edi-and-as2-status-reports.md)します。  
  
## <a name="status-report-filters-and-display-columns"></a>状態レポートのフィルターと列の表示  
 EDI および AS2 状態レポートには、状態レポート用に保存されるデータの範囲をカスタマイズすることができます。 行います、**グループ ハブ**のページ、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソール。 状態レポートのいずれかの状態レポート ペインを表示した後は、レポートに表示データの範囲を選択できます。 状態レポートのクエリ式に含めるフィルター値を選択するとこれを行います。  
  
 状態レポートに表示されるデータの種類をカスタマイズすることもできます。  
  
> [!NOTE]
>  状態レポートが有効になっているときにすべての状態は記憶域に保存されます。 クエリ式または状態列をカスタマイズするとは、表示する保存されたデータを定義します。  
  
 詳細については、次を参照してください。 [EDI および AS2 状態レポートを構成する](../core/configuring-an-edi-and-as2-status-report.md)します。  
  
## <a name="see-also"></a>参照  
 [EDI および AS2 状態レポート](../core/edi-and-as2-status-reporting.md)   
 [EDI インターチェンジし、関連する ACK の状態レポート](../core/edi-interchange-and-correlated-ack-status-report.md)   
 [バッチの状態レポート](../core/batch-status-report.md)   
 [インターチェンジの集計レポート](../core/interchange-aggregation-report.md)   
 [トランザクション セットの集計レポート](../core/transaction-set-aggregation-report.md)   
 [AS2 メッセージおよび関連する MDN の状態レポート](../core/as2-message-and-correlated-mdn-status-report.md)