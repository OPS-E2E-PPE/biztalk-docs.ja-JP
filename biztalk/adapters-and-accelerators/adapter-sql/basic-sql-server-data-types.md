---
title: 基本的な SQL Server データ型 |Microsoft Docs
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
ms.openlocfilehash: 083e3ff9887a991fe6d2d7a726cdb439abc50d5b
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65370034"
---
# <a name="basic-sql-server-data-types"></a>基本的な SQL Server データ型
このトピックで説明する方法、[!INCLUDE[adaptersql](../../includes/adaptersql-md.md)]サーフェスの基本的な SQL Server データ型。  
  
## <a name="supported-sql-server-data-types"></a>サポートされる SQL Server のデータ型  
 次の表は SQL Server のデータ型を表示する方法、 [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]:  
  
|SQL Server データ型|XSD 型|.NET の種類|コメント|  
|--------------------------|--------------|---------------|--------------|  
|Bigint|Long|Long|-|  
|Binary|Base64Binary|Byte[]|-|  
|bit|ブール値|Bool|-|  
|Char|String|String|-|  
|date|DateTime|DateTime|-|  
|DATETIME|DateTime|DateTime|[Datetime] フィールドにデータを書き込み中に、アダプターは常に GMT で時刻を格納します。 タイム ゾーン情報を指定する場合、アダプターを使用して、値を GMT の有効な値に変換とデータベース テーブルに書き込みます。 たとえば、12/31/12/31/2008 としてテーブルに書き込まれる 2008T23:59:59 + 5時 30分 6時 29分: 59 PM。<br /><br /> ただし、タイム ゾーン情報を指定しないと、アダプターは既に、GMT である値を考慮し、同じ値をテーブルに書き込みます。 たとえば、12/31/12/31/2008 としてテーブルに書き込まれる 2008T23:59:59 11時 59分: 59 PM。|  
|Datetime2|DateTime|DateTime|-|  
|Datetimeoffset|DateTime|DateTime|-|  
|10 進数|xsd:decimal 場合は、有効桁数 < = 28<br /><br /> xsd:string の場合は、有効桁数 28 >|Decimal の場合は、有効桁数 < = 28<br /><br /> 文字列の場合は、有効桁数 28 >|-|  
|Filestream|Base64Binary|Byte[]|-|  
|float|Double|Double|-|  
|Geography|String|String|-|  
|Geometry|String|String|-|  
|hierarchyid|String|String|-|  
|イメージ|Base64Binary|Byte[]|-|  
|Int|Int|Int|-|  
|money|10 進数|10 進数|-|  
|Nchar|String|String|-|  
|Ntext|String|String|-|  
|数値|10 進数|10 進数|-|  
|nvarchar|String|String|-|  
|Nvarchar (max)|String|String|-|  
|Real|float|float|-|  
|Smalldatetime|DateTime|DateTime|-|  
|Smallint|Short|Short|-|  
|Smallmoney|10 進数|10 進数|-|  
|SQLVariant|String|String|-|  
|テキスト|String|String|-|  
|Time|Duration|timespan|-|  
|Timestamp|Base64Binary|Byte[]|-|  
|Tinyint|unsignedByte|バイト|-|  
|一意識別子|{ http://schemas.microsoft.com/2003/10/Serialization/}:guid|Guid|-|  
|Varbinary|Base64Binary|Byte[]|-|  
|Varbinary(Max)|Base64Binary|Byte[]|-|  
|Varchar|String|String|-|  
|Varchar (max)|String|String|-|  
|XML|String|String|-|  
  
## <a name="see-also"></a>参照  
 [メッセージと BizTalk adapter for SQL Server のメッセージ スキーマ](../../adapters-and-accelerators/adapter-sql/messages-and-message-schemas-for-biztalk-adapter-for-sql-server.md)