---
title: WCF チャネル モデルを使用して SQL アプリケーションを開発 |Microsoft ドキュメント
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
ms.openlocfilehash: 7b503b0766a4848e05c9361fb151196ee43afd81
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22222234"
---
# <a name="develop-sql-applications-using-the-wcf-channel-model"></a>WCF チャネル モデルを使用して SQL アプリケーションを開発します。
使用することができます、[!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)]チャネル モデルを使用する、 [!INCLUDE[adaptersql](../../includes/adaptersql-md.md)] SQL サーバー バインドで作成されたチャネル インスタンス経由で直接 XML メッセージを送信することによってです。  
  
 厳密に型指定されたクラスと、WCF サービス モデルを公開するメソッドを使用する場合より、WCF チャネル モデルを使用する利点の 1 つは、チャネル モデルが SQL データベースで実行する操作をより詳細に制御を提供することです。 このコントロールは、ファクトのことで、WCF チャネル モデルを直接制御するチャネル経由で送信するメッセージの内容から取得されます。  
  
 特定のシナリオでは、この余分なレベルの制御と役に立つことがあります。 たとえば、WCF チャネル モデルを使用して、テーブルの更新操作を実行するときに、ターゲット行の列をメッセージを渡すテンプレートの更新からの列を省略することでに更新できます選択的にします。 必要な列のみが"nillable = false"、WSDL でします。 によって公開されている、update メソッドを[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]クライアントは、テーブルのスキーマ内のすべての列を含むテンプレートに対してレコードの厳密に型指定されたパラメーターを使用します。  
  
 このトピックのセクションでは、操作を実行する方法を説明する、 [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] WCF チャネル モデルを使用します。  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [SQL アダプタを使用して WCF チャネル モデルの概要](../../adapters-and-accelerators/adapter-sql/overview-of-the-wcf-channel-model-with-the-sql-adapter.md)  
  
-   [SQL アダプターを使用して、チャネルを作成します。](../../adapters-and-accelerators/adapter-sql/create-a-channel-using-the-sql-adapter.md)  
  
-   [WCF チャネル モデルを使用して SQL でのテーブルに対して挿入操作の実行します。](../../adapters-and-accelerators/adapter-sql/run-an-insert-operation-on-a-table-in-sql-using-the-wcf-channel-model.md)  
  
-   [WCF チャネル モデルを使用して SQL Server からデータ変更のポーリングに基づいたメッセージを受信します。](../../adapters-and-accelerators/adapter-sql/receive-polling-based-data-changed-messages-from-sql-server-using-a-wcf-channel.md)  
  
## <a name="see-also"></a>参照  
[SQL アプリケーションを開発します。](../../adapters-and-accelerators/adapter-sql/develop-your-sql-applications.md)