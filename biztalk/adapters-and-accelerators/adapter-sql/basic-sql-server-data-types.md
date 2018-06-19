---
title: 基本的な SQL Server データ型 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f744fe14-4134-486d-b060-9ac2d5f21c56
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a8e60816dc362fc4630e263397048bcdee8d774b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22222618"
---
# <a name="basic-sql-server-data-types"></a>基本的な SQL Server データ型
このトピックの内容について説明しますが、どのように[!INCLUDE[adaptersql](../../includes/adaptersql-md.md)]サーフェスの基本的な SQL Server データ型。  
  
## <a name="supported-sql-server-data-types"></a>サポートされる SQL Server のデータ型  
 次の表で、SQL Server データ型を表示する方法を示しています、 [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]:  
  
|SQL Server データ型|XSD 型|.NET の種類|コメント|  
|--------------------------|--------------|---------------|--------------|  
|Bigint|Long|Long|-|  
|Binary|Base64Binary|Byte[]|-|  
|bit|ブール値|Bool|-|  
|Char|文字列|文字列|-|  
|日付|DateTime|DateTime|-|  
|DateTime|DateTime|DateTime|Datetime フィールドにデータを書き込み中に、アダプターは常に GMT で時刻を格納します。 タイム ゾーン情報を指定する場合、アダプターはを使用して有効な gmt 時刻値に値を変換して、データベース テーブルに書き込みます。 たとえば、12/31/12/31/2008 としてテーブルに書き込まれる 2008T23:59:59 + 5時 30分 6時 29分: 59 PM。<br /><br /> ただし、タイム ゾーン情報を指定しないと、アダプターは既に、GMT である値を考慮し、テーブルに同じ値を書き込みます。 たとえば、12/31/12/31/2008 としてテーブルに書き込まれる 2008T23:59:59 11時 59分: 59 PM。|  
|Datetime2|DateTime|DateTime|-|  
|Datetimeoffset|DateTime|DateTime|-|  
|Decimal|xsd:decimal 場合は、有効桁数 < = 28<br /><br /> xsd:string の場合は、有効桁数 28 >|Decimal の場合は、有効桁数 < = 28<br /><br /> 文字列の場合は、有効桁数 28 >|-|  
|Filestream|Base64Binary|Byte[]|-|  
|Float|Double|Double|-|  
|Geography|文字列|文字列|-|  
|Geometry|文字列|文字列|-|  
|Hierarchyid|文字列|文字列|-|  
|[イメージ]|Base64Binary|Byte[]|-|  
|int|int|int|-|  
|Money|Decimal|Decimal|-|  
|Nchar|文字列|文字列|-|  
|Ntext|文字列|文字列|-|  
|数値|Decimal|Decimal|-|  
|nvarchar|文字列|文字列|-|  
|Nvarchar (max)|文字列|文字列|-|  
|Real|Float|Float|-|  
|Smalldatetime|DateTime|DateTime|-|  
|Smallint|Short|Short|-|  
|Smallmoney|Decimal|Decimal|-|  
|SQLVariant|文字列|文字列|-|  
|テキスト|文字列|文字列|-|  
|[時刻]|Duration|Timespan|-|  
|Timestamp|Base64Binary|Byte[]|-|  
|Tinyint|UnsignedByte|Byte|-|  
|一意識別子|{http://schemas.microsoft.com/2003/10/Serialization/}: guid|Guid|-|  
|Varbinary|Base64Binary|Byte[]|-|  
|Varbinary (max)|Base64Binary|Byte[]|-|  
|Varchar|文字列|文字列|-|  
|Varchar (max)|文字列|String|-|  
|XML|String|文字列|-|  
  
## <a name="see-also"></a>参照  
 [メッセージと BizTalk Adapter for SQL Server のメッセージ スキーマ](../../adapters-and-accelerators/adapter-sql/messages-and-message-schemas-for-biztalk-adapter-for-sql-server.md)