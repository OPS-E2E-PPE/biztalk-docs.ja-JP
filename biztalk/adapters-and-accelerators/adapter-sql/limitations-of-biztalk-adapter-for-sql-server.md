---
title: "BizTalk adapter for SQL Server の制限事項 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 5a19b109-a6b7-452f-a544-48627fa52f36
caps.latest.revision: "15"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c5a80990a9e3f417b64a06d8823300d53b2c4f3b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="limitations-of-biztalk-adapter-for-sql-server"></a>BizTalk adapter for SQL Server の制限事項
次はの既知の制限[!INCLUDE[adaptersql](../../includes/adaptersql-md.md)]:  
  
-   [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]は SQL Server データベースに作成されたシノニムをサポートしていません。 SQL Server でのシノニムについて、次を参照してください。 [http://go.microsoft.com/fwlink/?LinkId=120111](http://go.microsoft.com/fwlink/?LinkId=120111)です。  
  
-   実行するコンピューターのシステム時刻を変更するかどうか、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]ホスト、時間が自動的に更新されませんで、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]ホストします。 受信ポートを使用する受信操作の不適切な動作する可能性が[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]です。 この問題を回避するを実行するコンピューターのシステム時刻を変更した後、受信ポートを持つホスト インスタンスを再起動する必要があります。  
  
-   ストアド プロシージャのパラメーター名が 127 以上の文字が含まれている場合は、ストアド プロシージャを使用して、実行することはできません、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]です。 これは、ADO.NET の制限のためです。  
  
-   WSDL、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]プロキシに変換すると、生成された場合、System.DateTime として DateTimeOffset 列を公開します。 このデータ型は、タイム ゾーン情報を格納できません。 結果として、アダプターの送信プロキシに任意の日付/時刻値は、.NET アプリケーションでのローカル時刻に変換されます。 タイム ゾーン情報を保持する場合は、System.DateTime ではなく、文字列型を使用するプロキシのインターフェイスを変更する必要があります。 XmlConvert.ToDateTimeOffset を使用してのタイム ゾーン情報を格納する、Sytstem.DateTimeOffset オブジェクトを作成します。  
  
## <a name="see-also"></a>参照  
 [SQL Server の BizTalk アダプターを理解します。](../../adapters-and-accelerators/adapter-sql/understand-biztalk-adapter-for-sql-server.md)