---
title: "BizTalk adapter for Oracle E-business Suite の制限事項 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 149cee03-43cd-4cb3-a937-6565f5e96ce5
caps.latest.revision: "27"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e7611c56fbd24c7c7cf09d38d376df585b72b284
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="limitations-of-biztalk-adapter-for-oracle-e-business-suite"></a>BizTalk adapter for Oracle E-business Suite の制限事項
## <a name="general-limitations"></a>一般的な制限事項  
 次はの既知の制限[!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)]:  
  
-   [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] XML Gateway、アドバンスド キュー、およびビジネス イベントはサポートされません。  
  
     ただし、次のように、ビジネス イベントの制限を回避することができます。  
  
    1.  Oracle のビジネス イベント システムでは、プロシージャを呼び出すカスタム PL/SQL ビジネス イベント発生時にサブスクリプションを作成します。  
  
    2.  ビジネス イベントを受け取るカスタム PL/SQL プロシージャを記述します。  
  
    3.  テーブルに結果データ (イベントおよびイベント ペイロード) を格納するカスタムの PL/SQL 手順に従います。  
  
    4.  使用して、[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]をポーリングまたはテーブルから通知を受信します。  
  
-   [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] XML 型をサポートしていません。  
  
-   [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]を NULL に VARRAY で最初の要素の値を設定するクライアントを有効にしません。  
  
-   [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]のフィールドを含むサポート レコードいないは、レコード型の PL/SQL テーブルを入力します。  
  
-   [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]循環参照が含まれるユーザー定義型 (Udt) をサポートしていません。  
  
-   [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] (レコード型、テーブルの種類、UDT、および VARRAY) などの複合型の内部 BFILE データ型をサポートしていません。  
  
-   [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]のみに最大 2 つのレベルの入れ子の UDT をサポートしています。  
  
-   PL/SQL テーブルを除く、[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]はパッケージ内で定義されている Udt をサポートしていません。  
  
-   BizTalk Server にアダプターを使用する場合は、WCF カスタム資格情報の送信ポートが正しくない場合、要求メッセージは処理されません。 正しい資格情報を指定すると後、は、Oracle E-business Suite にメッセージを送信し、応答を受信します。 ただし、応答メッセージでは、出力ポートを使用できません。 このようなシナリオでは、ホスト インスタンスを再起動する必要があります。  
  
## <a name="limitations-due-to-odpnet"></a>ODP.NET のための制限事項  
 次はの既知の制限[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]ODP.NET の制限のため。  
  
-   [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]数値フィールドをインデックス化されていない PL/SQL テーブルをサポートしていません。  
  
-   [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]は含まれていない任意の要素の連想配列をサポートしていません。  
  
-   [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]はローカル タイム ゾーンの属性 (TimeStampLTZ) を持つ TimeStamp データ型が含まれている Udt をサポートしていません。  
  
-   [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] Udt を含むをサポートしていない、"です"。 (期間)、名前にします。  
  
-   [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] IN OUT パラメーターとして BLOB、CLOB、および NCLOB データ型が含まれている Udt をサポートしていません。  
  
-   [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] Varray の Varray の次の単純型をサポートしていません: BFILE、IntervalDS、IntervalYM、TimeStampLTZ、および TimeStampTZ です。  
  
-   連想配列の制限、により PL/SQL テーブルまたはデータ型を次のいずれかが含まれるレコードの PL/SQL テーブルでサポートされていない、 [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]:  
  
    -   BFILE  
  
    -   BLOB  
  
    -   CLOB  
  
    -   IntervalDS  
  
    -   IntervalYM  
  
    -   Long  
  
    -   NCLOB  
  
    -   RowID  
  
    -   TimeStamp  
  
    -   TimeStampLTZ  
  
    -   TimeStampTZ  
  
## <a name="see-also"></a>参照  
 [Oracle E-business Suite の BizTalk アダプターを理解します。](../../adapters-and-accelerators/adapter-oracle-ebs/understand-biztalk-adapter-for-oracle-e-business-suite.md)