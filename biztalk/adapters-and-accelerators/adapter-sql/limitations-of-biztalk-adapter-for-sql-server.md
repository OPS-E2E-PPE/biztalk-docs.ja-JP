---
title: SQL Server 用 BizTalk アダプターの制限事項 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 5a19b109-a6b7-452f-a544-48627fa52f36
caps.latest.revision: 15
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 195701e4bba469a7faaab36a5ae1636c5abca5f4
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36967387"
---
# <a name="limitations-of-biztalk-adapter-for-sql-server"></a>SQL Server 用 BizTalk アダプターの制限事項
次の制限事項を呼びます[!INCLUDE[adaptersql](../../includes/adaptersql-md.md)]:  
  
- [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]は SQL Server データベースに作成されたシノニムをサポートしていません。 SQL Server でのシノニムについては、次を参照してください。 [ http://go.microsoft.com/fwlink/?LinkId=120111](http://go.microsoft.com/fwlink/?LinkId=120111)します。  
  
- 実行するコンピューターのシステム時刻を変更するかどうか、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]ホスト、時間が自動的に更新されないで、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]ホスト。 受信ポートを使用する受信操作の不適切な動作になる可能性[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]します。 この問題を回避するを実行するコンピューターのシステム時刻を変更した後、受信ポートを持つホスト インスタンスを再起動する必要があります。  
  
- ストアド プロシージャでパラメーター名は 127 以上の文字が含まれる場合は、ストアド プロシージャを使用して、実行することはできません、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]します。 これは、ADO.NET の制限のため。  
  
- WSDL、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]プロキシに変換されるときに生成されますが、System.DateTime として DateTimeOffset 列を公開します。 このデータ型は、タイム ゾーン情報を格納できません。 結果として、アダプターが送信プロキシを任意の日付/時刻値は、.NET アプリケーションでのローカル時刻に変換されます。 タイム ゾーンの情報を保持する場合は、System.DateTime の代わりに、文字列型を使用するプロキシのインターフェイスを変更する必要があります。 次に、XmlConvert.ToDateTimeOffset を使用して、タイム ゾーン情報を格納できる Sytstem.DateTimeOffset オブジェクトを作成します。  
  
## <a name="see-also"></a>参照  
 [BizTalk Adapter for SQL Server についてください。](../../adapters-and-accelerators/adapter-sql/understand-biztalk-adapter-for-sql-server.md)