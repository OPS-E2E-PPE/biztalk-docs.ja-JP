---
title: WCF チャネル モデルを使用して SQL アプリケーションの開発 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 11df5cc2-b532-45a8-9055-d05f4704a6e5
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0bf7b12a076e88cd59dcc463dd8c10bd0817e612
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65369867"
---
# <a name="develop-sql-applications-using-the-wcf-channel-model"></a>WCF チャネル モデルを使用して SQL アプリケーションを開発します。
使用することができます、[!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)]チャネル モデルを使用する、 [!INCLUDE[adaptersql](../../includes/adaptersql-md.md)] SQL サーバー バインドで作成されたチャネル インスタンス経由で直接 XML メッセージを送信することです。  
  
 WCF チャネル モデルを使用して、厳密に型指定されたクラスと、WCF サービス モデルを公開するメソッドを使用する利点の 1 つは、チャネル モデルが SQL データベースで実行する操作のきめの細かい制御を提供します。 このコントロールは、ファクトのことで WCF チャネル モデルを直接制御チャネル経由で送信するメッセージの内容から取得されます。  
  
 特定のシナリオでこの追加レベルの制御はパフォーマンスを向上することはできます。 たとえば、WCF チャネル モデルを使用して、テーブルに対する Update 操作を実行するときに選択的に更新できますターゲット行内の列、メッセージを渡すテンプレートの更新からの列を省略することで。 必要な列のみが"nillable = false"、WSDL でします。 によって公開されている、update メソッドを[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]クライアントで、テーブルのスキーマ内のすべての列を含むテンプレートのレコードの厳密に型指定されたパラメーターを使用します。  
  
 このトピックのセクションでは、操作を実行する方法を説明します、 [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] WCF チャネル モデルを使用しています。  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [SQL アダプターを使用した WCF チャネル モデルの概要](../../adapters-and-accelerators/adapter-sql/overview-of-the-wcf-channel-model-with-the-sql-adapter.md)  
  
-   [SQL アダプタを使用するチャネルを作成します。](../../adapters-and-accelerators/adapter-sql/create-a-channel-using-the-sql-adapter.md)  
  
-   [WCF チャネル モデルを使用して SQL テーブルで挿入操作を実行します。](../../adapters-and-accelerators/adapter-sql/run-an-insert-operation-on-a-table-in-sql-using-the-wcf-channel-model.md)  
  
-   [WCF チャネル モデルを使用して SQL Server からのポーリングに基づいたデータ変更メッセージを受信します。](../../adapters-and-accelerators/adapter-sql/receive-polling-based-data-changed-messages-from-sql-server-using-a-wcf-channel.md)  
  
## <a name="see-also"></a>参照  
[SQL アプリケーションを開発する](../../adapters-and-accelerators/adapter-sql/develop-your-sql-applications.md)