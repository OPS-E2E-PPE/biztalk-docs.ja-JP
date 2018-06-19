---
title: '手順 6 (社内): 作成、キューから Insert スキーマへのメッセージをマップする変換 |Microsoft ドキュメント'
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
ms.openlocfilehash: 02b2be9659714beb4b9a52f4c2a9dd1e5b3ea47f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22276594"
---
# <a name="step-6-on-premises-create-a-transform-to-map-the-message-from-the-queue-to-the-insert-schema"></a>手順 6 (社内): キューから Insert スキーマへのメッセージをマップする変換を作成します。
によって受信されるメッセージ[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]Service Bus キューからでは、 **ECommerceSalesOrder.xsd**スキーマです。 ただしにメッセージを挿入する、 **SalesOrder**テーブルでのメッセージがある必要があります**挿入**で生成したスキーマ[手順 5 (オンプレミス): にメッセージを挿入するためのスキーマの生成SalesOrder テーブル](../core/step-5-generate-the-schema-for-inserting-a-message-into-salesorder-table.md)です。 そのため、このトピックでは作成を変換するマップ、 **ECommerceSalesOrder.xsd** Insert 操作スキーマにスキーマです。  
  
### <a name="to-create-a-map"></a>マップを作成するには  
  
1.  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]をポイントし、プロジェクトを右クリックし、作成されると、既に**追加**、クリックして**新しい項目の**します。 **新しい項目の**ダイアログ ボックスで、**マップ**、マップ名を入力`SalesOrder_SQL.btm`、順にクリック**追加**です。  
  
2.  マップでは、送信元スキーマの選択**ECommerceSalesOrder.xsd**です。 送信先スキーマの選択**TableOperations.SalesOrder.xsd (Insert)** スキーマです。  
  
3.  送信元スキーマと送信先スキーマで次のノードを直接マップします。  
  
    |送信元スキーマ|送信先スキーマ|  
    |-------------------|------------------------|  
    |CompanyCode|CompanyCode|  
    |PartId|PartNum|  
    |Quantity|Qty|  
    |AskPrice|UnitAskPrice|  
    |コメント|CustomerComments|  
  
4.  使用して、**日付と時刻**に値をマップする functoid、 **DateRequested**と**ShipDate**送信先スキーマ内の要素。 これらのノードは送信元スキーマの各ノードにマップされません。 代わりに、現在の日付と時刻に渡されるでこれらのノードを使用して、**日付と時刻**functoid です。  
  
    1.  ドラッグ アンド ドロップ、**日付と時刻**マッパー画面にツールボックスから functoid です。  
  
    2.  Functoid への接続、 **DateRequested**送信先スキーマ内の要素。  
  
    3.  ドラッグ アンド ドロップ別**日付と時刻**functoid に接続するには**ShipDate**送信先スキーマ内の要素。  
  
5.  次のノードを使用して、送信元と送信先スキーマのマップ、**文字列連結**functoid:  
  
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
  
     文字列連結マッピング セットごとに、次の手順を実行します。  
  
    1.  ドラッグ アンド ドロップ、**文字列連結**マッパー画面にツールボックスから functoid です。  
  
    2.  入力としてソース ツリーから各要素を追加、**文字列連結**functoid です。  
  
    3.  ドラッグ アンドの出力を構成、**文字列連結**functoid を送信先スキーマ内の要素。  
  
         完成したマップは次のようになります。  
  
         ![スキーマを変換するマップ](../core/media/bts2010r2-tut1-map.jpg "BTS2010R2_Tut1_Map")  
  
## <a name="see-also"></a>参照  
 [チュートリアル 4: BizTalk Server 2013 を使用するハイブリッド アプリケーションを作成します。](../core/tutorial-4-creating-a-hybrid-application-using-biztalk-server-2013.md)