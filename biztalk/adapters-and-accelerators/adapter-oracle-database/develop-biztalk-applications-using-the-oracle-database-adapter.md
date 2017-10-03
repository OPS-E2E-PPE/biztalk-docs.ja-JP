---
title: "Oracle データベース アダプターを使用して BizTalk アプリケーションを開発 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Content-Based Routing (CBR)
- BizTalk orchestrations, using orchestrations to perform operations
ms.assetid: 65689c83-4a57-4aad-b0e9-f1bad901a7b9
caps.latest.revision: "14"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fa1b3f688987c0c8339a2fd81c1b1ddf67128818
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="develop-biztalk-applications-using-the-oracle-database-adapter"></a>Oracle データベース アダプターを使用して BizTalk アプリケーションを開発します。
BizTalk アプリケーションの開発で BizTalk プロジェクトを作成する[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]を使用して、 [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)] XML スキーマを生成します。 スキーマが生成されると、コンテンツ ベースのルーティング (CBR) を使用するか、生成されたスキーマに準拠するメッセージを送受信する BizTalk オーケストレーションを作成します。  
  
 CBR は、ここで、Oracle データベースに送信されるメッセージには、処理を要する処理は不要のシナリオで使用できます。 たとえば、受信ポートが特定の型だけのメッセージを受信することがわかっている場合は、送信ポートにフィルター式と一致するメッセージをルーティングする送信ポートにフィルターを追加できます。  
  
 、BizTalk オーケストレーションの送信を作成およびとの間でメッセージを送受信する受信ポート、 [!INCLUDE[wcfadapter_short](../../includes/wcfadapter-short-md.md)]、さらに、メッセージを送信する[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]です。 このセクションでは、BizTalk オーケストレーションを使用して Oracle データベースを使用して、操作を実行するに関する情報を提供、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]です。 [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]順番に使用して、 [!INCLUDE[wcfadapter_short](../../includes/wcfadapter-short-md.md)]、WCF バインドと対話することができます。  
  
> [!IMPORTANT]
>  使用する、 [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] microsoft [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]、常に設定する必要があります、 **EnableBizTalkCompatibilityMode**にプロパティのバインド**True**です。 バインドのプロパティを設定する方法については、次を参照してください。 [Oracle データベースのバインドのプロパティを構成する](../../adapters-and-accelerators/adapter-oracle-database/configure-the-binding-properties-for-oracle-database.md)です。  
  
> [!IMPORTANT]
>  [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]に含まれている[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]BizTalk Server 管理コンソールには表示されません。 アダプター、[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]は WCF ベースし、WCF カスタム バインドを使用します。 BizTalk Server 管理コンソールに表示されます、[!INCLUDE[wcfadapter_short](../../includes/wcfadapter-short-md.md)]です。 これがない自動的に表示、WCF カスタム バインドし、したがって WCF ベースが表示されない[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]です。  
> 
> また、メタデータを生成する、使用して、[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]です。 使用しないで、[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]です。 使用方法について、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]を参照してください[Visual Studio での Oracle データベース操作のメタデータを取得](../../adapters-and-accelerators/adapter-oracle-database/get-metadata-for-oracle-database-operations-in-visual-studio.md)です。 
> 
> アダプター バージョン間の相違点は、次を参照してください。[を移行する BizTalk プロジェクトが作成を使用して BizTalk ODBC Adapter 用 Oracle Database](http://msdn.microsoft.com/library/18f40265-c7f3-44a1-99b6-1b1dc800561e)です。  
  
  
  
## <a name="see-also"></a>参照  
[Oracle データベース アプリケーションを開発します。](../../adapters-and-accelerators/adapter-oracle-database/develop-your-oracle-database-applications.md)