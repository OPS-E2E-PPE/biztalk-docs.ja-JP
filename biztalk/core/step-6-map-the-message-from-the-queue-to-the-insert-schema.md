---
title: 手順 6 (オンプレミス):キューから Insert スキーマにメッセージをマップする変換を作成 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 30a55f1e-32cc-409a-a814-084026f51b35
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 382d408e1fdacbbdc6efe151eb7cf53286d497e8
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65244294"
---
# <a name="step-6-on-premises-create-a-transform-to-map-the-message-from-the-queue-to-the-insert-schema"></a>手順 6 (オンプレミス):キューから Insert スキーマにメッセージをマップする変換を作成します。
受信されるメッセージ[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]、Service Bus キューからになります、 **ECommerceSalesOrder.xsd**スキーマ。 ただしにメッセージを挿入する、 **SalesOrder**テーブルのメッセージがある必要があります**挿入**で生成したスキーマ[手順 5 (オンプレミス)。メッセージする SalesOrder テーブルを挿入するためのスキーマを生成](../core/step-5-generate-the-schema-for-inserting-a-message-into-salesorder-table.md)します。 変換するマップを作成このトピックで、 **ECommerceSalesOrder.xsd** Insert 操作スキーマにスキーマ。  

### <a name="to-create-a-map"></a>マップを作成するには  

1. [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]プロジェクトを右クリックをポイントして、既に作成した、**追加**、順にクリックします**新しい項目の**します。 **新しい項目の**ダイアログ ボックスで、**マップ**、マップ名として入力`SalesOrder_SQL.btm`、順にクリックします**追加**。  

2. 送信元スキーマ、マップで選択**ECommerceSalesOrder.xsd**します。 送信先スキーマでは、選択**TableOperations.SalesOrder.xsd (Insert)** スキーマ。  

3. 元と送信先スキーマの次のノードを直接マップするには。  


   | 送信元スキーマ | 送信先スキーマ |
   |---------------|--------------------|
   |  CompanyCode  |    CompanyCode     |
   |    PartId     |      PartNum       |
   |   Quantity    |        Qty         |
   |   AskPrice    |    UnitAskPrice    |
   |   コメント    |  CustomerComments  |


4. 使用して、**日付と時刻**に値をマップの functoid、 **DateRequested**と**ShipDate**送信先スキーマ内の要素。 これらのノードは、送信元スキーマ内の各ノードにマップされていません。 代わりに、現在の日付と時刻に渡されますが、これらのノードを使用して、**日付と時刻**functoid。  

   1.  ドラッグ アンド ドロップ、**日付と時刻**マッパー画面にツールボックスから functoid。  

   2.  Functoid を接続、 **DateRequested**送信先スキーマ内の要素。  

   3.  ドラッグ アンド ドロップ別**日付と時刻**functoid に接続し、 **ShipDate**送信先スキーマ内の要素。  

5. 次のノードを使用して元と送信先スキーマでマップを**文字列連結**functoid:  

   |送信元スキーマ|送信先スキーマ|  
   |-------------------|------------------------|  
   |Address\Line1|SellToAddress<br /><br /> BillToAddress|  
   |Address\Line2|SellToAddress<br /><br /> BillToAddress|  
   |Address\City|SellToAddress<br /><br /> BillToAddress|  
   |Address\State|SellToAddress<br /><br /> BillToAddress|  
   |Address\Country|SellToAddress<br /><br /> BillToAddress|  
   |Address\ZipCode|SellToAddress<br /><br /> BillToAddress|  
   |Contact\FirstName|PartnerContact|  
   |Contact\LastName||  

    文字列の連結マッピング セットごとに、次の手順に従います。  

   1.  ドラッグ アンド ドロップ、**文字列連結**マッパー画面にツールボックスから functoid。  

   2.  入力としてソース ツリーから各要素を追加、**文字列連結**functoid。  

   3.  ドラッグ アンドの出力を構成、**文字列連結**functoid を送信先スキーマ内の要素。  

        完成したマップには、次のようになります。  

        ![スキーマを変換するマップ](../core/media/bts2010r2-tut1-map.jpg "BTS2010R2_Tut1_Map")  

## <a name="see-also"></a>参照  
 [チュートリアル 4: BizTalk Server 2013 を使用してハイブリッド アプリケーションを作成します。](../core/tutorial-4-creating-a-hybrid-application-using-biztalk-server-2013.md)