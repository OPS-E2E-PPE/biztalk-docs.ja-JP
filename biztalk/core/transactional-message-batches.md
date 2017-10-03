---
title: "トランザクション メッセージ バッチ |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b1790c05-e3f7-4667-8a9e-f6f208e55e40
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 28be423aa500ba8950b5b2100ce68dba7743bd79
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="transactional-message-batches"></a>トランザクション メッセージ バッチ
一部のアダプターは、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] トランザクションに合わせて外部トランザクションを調整する必要があります。 たとえば、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] に付属の SQL アダプターは、[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] トランザクションに合わせて [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] トランザクションを調整する必要があります。 そのためには、アダプターが [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] トランザクション オブジェクトにアクセスする必要があります。 トランザクション オブジェクトは明示的に作成され、バッチに関連付けられます。その後、そのバッチが [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] に送信されます。 トランザクション オブジェクトが関連付けられているバッチを "トランザクション バッチ" といいます。 独自の Microsoft 分散トランザクション コーディネーター (MSDTC) トランザクション オブジェクトを指定することによって、トランザクションから [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] へ、および  からトランザクションへ、"確実に 1 回だけ" データを配信できます。  
  
 SQL アダプターのようなトランザクション データベース アダプターは、バッチに使用される 1 つのトランザクションが原因で外部データベースにデッドロックを引き起こす可能性があります。 このため、SQL アダプターのバッチ サイズは特定の値にハードコードされています。  
  
 トランザクションのスコープ内で、アダプターが別のデータベースや MSMQ などの追加リソース マネージャーを参加させる必要がある場合は、明示的な外部トランザクションを作成し、メッセージング エンジンに渡す必要があります。 外部トランザクションを作成し、それをバッチに関連付けることは、トランザクション バッチと呼ばれます。 トランザクション アダプターは、外部の Microsoft 分散トランザクション コーディネーター (MSDTC) トランザクションを明示的に作成してトランザクション バッチの使用するようにするアダプターです。  
  
 アダプターが [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] にトランザクションを送信する理由の 1 つは、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] または外部システムにデータのレコードを作成するためです。 このレコードによって、メッセージが確実に一度だけ配信されるようになります。  
  
> [!NOTE]
>  MSDTC の詳細については、の分散トランザクション コーディネーターのマニュアルを参照してください: [http://go.microsoft.com/fwlink/?LinkId=44297](http://go.microsoft.com/fwlink/?LinkId=44297)です。  
  
 ファイル アダプターは、管理対象となる外部ファイル操作がトランザクションではないためトランザクションへのアクセスを必要としないアダプターの一例です。 この場合、アダプターはトランザクション オブジェクトを [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] に送信しません。 一方、SQL アダプターは SQL データベースと連携し、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] メッセージ処理以外の操作を行う可能性があります。 その場合、SQL アダプターは MSDTC トランザクションを [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] へ渡します。  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [トランザクションの処理](../core/handling-transactions.md)