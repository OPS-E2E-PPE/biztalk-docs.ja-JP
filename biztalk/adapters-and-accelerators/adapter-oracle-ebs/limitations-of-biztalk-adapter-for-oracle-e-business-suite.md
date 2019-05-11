---
title: BizTalk adapter for Oracle E-business Suite の制限事項 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 149cee03-43cd-4cb3-a937-6565f5e96ce5
caps.latest.revision: 27
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b8a03cf97fa031a1e5b141fab79c3711e744bd49
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65375419"
---
# <a name="limitations-of-biztalk-adapter-for-oracle-e-business-suite"></a>BizTalk adapter for Oracle E-business Suite の制限事項
## <a name="general-limitations"></a>一般的な制限事項  
 次の制限事項を呼びます[!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)]:  
  
- [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] XML ゲートウェイ、アドバンスド キュー、およびビジネス イベントはサポートされません。  
  
   ただし、次のように、ビジネス イベントの制限を回避取得できます。  
  
  1. Oracle のビジネス イベント システムでは、ビジネス イベントが発生したときに、カスタム PL/SQL プロシージャを呼び出すためのサブスクリプションを作成します。  
  
  2. ビジネス イベントを受け取るカスタム PL/SQL プロシージャを記述します。  
  
  3. テーブルに結果のデータ (イベントとイベント ペイロード) を格納するのにには、カスタムの PL/SQL 手順を使用します。  
  
  4. 使用して、[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]ポーリングまたはテーブルから通知を受信します。  
  
- [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] XML 型をサポートしていません。  
  
- [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] Null の VARRAY で最初の要素の値を設定するクライアントを有効にしません。  
  
- [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]のフィールドを含むレコードのないサポートは、レコードの種類の PL/SQL テーブルを入力します。  
  
- [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]は循環参照があるユーザー定義型 (Udt) をサポートしていません。  
  
- [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] (レコードの種類、テーブル型、UDT、および VARRAY) などの複合型、BFILE データ型をサポートしていません。  
  
- [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]のみに最大 2 つのレベルの入れ子の UDT をサポートしています。  
  
- PL/SQL のテーブルを除く、[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]はパッケージ内で定義されている Udt をサポートしていません。  
  
- BizTalk Server でアダプターを使用する場合は、WCF カスタム資格情報の送信ポートが正しくない、要求メッセージは処理されません。 正しい資格情報を指定すると、Oracle E-business Suite にメッセージを送信し、応答を受信します。 ただし、応答メッセージでは、出力ポートを使用できません。 このようなシナリオでは、ホスト インスタンスを再起動する必要があります。  
  
## <a name="limitations-due-to-odpnet"></a>ODP.NET に関する制約  
 次の制限事項を呼びます[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]ODP.NET の制限のため。  
  
- [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]数値フィールドでインデックス化されていない PL/SQL テーブルをサポートしません。  
  
- [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]は任意の要素が含まれていない連想配列をサポートしていません。  
  
- [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]はローカル タイム ゾーンの属性 (TimeStampLTZ) を持つ TimeStamp データ型が含まれている Udt をサポートしていません。  
  
- [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]が含まれている Udt をサポートしていませんが、"." (期間)、名前にします。  
  
- [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] IN OUT パラメーターとして BLOB、CLOB、NCLOB データ型が含まれている Udt をサポートしていません。  
  
- [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] Varray の Varray の次の単純型をサポートしていません。BFILE、IntervalDS、IntervalYM、TimeStampLTZ、および TimeStampTZ します。  
  
- 連想配列の制限のため PL/SQL テーブルまたは次のデータ型のいずれかが含まれているレコードの PL/SQL テーブルでサポートされていない、 [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]:  
  
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
 [BizTalk Adapter for Oracle E-Business Suite について](../../adapters-and-accelerators/adapter-oracle-ebs/understand-biztalk-adapter-for-oracle-e-business-suite.md)