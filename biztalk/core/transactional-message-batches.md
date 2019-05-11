---
title: トランザクション メッセージ バッチ |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b1790c05-e3f7-4667-8a9e-f6f208e55e40
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bbc6d3a450106df1b67aa2c0e8fb1ada2f1a9e95
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65399223"
---
# <a name="transactional-message-batches"></a>トランザクション メッセージ バッチ
一部のアダプターが内部と外部トランザクションを調整する必要があります[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]トランザクション。 たとえば、SQL アダプターが付属[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]調整する必要があります、[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]でトランザクションを[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]トランザクション。 これを行うには、アダプターへのアクセスを必要があります、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]トランザクション オブジェクトです。 トランザクション オブジェクトが明示的に作成され、バッチに送信する前に、バッチに関連付けられている[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]します。 関連付けられているトランザクション オブジェクトを持っているバッチはトランザクション バッチと呼ばれます。 Microsoft 分散トランザクション コーディネーター (MSDTC) トランザクション オブジェクトを指定することによって、「確実、一度だけ」を実現できますの入出力データの配信[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]します。  
  
 SQL アダプターのようなトランザクション データベース アダプター バッチに使用する 1 つのトランザクションのため外部データベースのデッドロックを引き起こす可能性があります。 これは、SQL アダプタのバッチ サイズが 1 つにハード コードされた理由です。  
  
 アダプターが別のデータベースや MSMQ などの追加リソース マネージャーをトランザクションのスコープ内に参加する必要があることを作成し、明示的な外部トランザクションをメッセージング エンジンに渡します。 外部トランザクションを作成し、バッチに関連付けることと呼ばれますが、トランザクション バッチ。 トランザクション アダプターは、トランザクション バッチは、アダプターを使用して、外部の Microsoft 分散トランザクション コーディネーター (MSDTC) トランザクションを明示的に作成しています。  
  
 アダプターを提供する理由の 1 つ[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]トランザクションでは、確認するどちらかが[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]または外部システムがデータのレコード。 このレコードにより、メッセージが 1 回だけ配信されるようになります。  
  
> [!NOTE]
>  MSDTC の詳細についてでの分散トランザクション コーディネーターのマニュアルを参照してください: [ http://go.microsoft.com/fwlink/?LinkId=44297](http://go.microsoft.com/fwlink/?LinkId=44297)します。  
  
 ファイル アダプターは、トランザクションへのアクセス、外部のファイル操作を管理するため、いないトランザクションを必要としないアダプターの例を示します。 この場合、アダプターがトランザクション オブジェクトを提供しない[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]します。 その一方で、SQL アダプターと対話し、SQL database、以外の追加操作があります、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]メッセージ処理します。 外部の MSDTC トランザクションはこの場合、アダプターに渡すには意味を行うことがあります[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]します。  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [トランザクションの処理](../core/handling-transactions.md)