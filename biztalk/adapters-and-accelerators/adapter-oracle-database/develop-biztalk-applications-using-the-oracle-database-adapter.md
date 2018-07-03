---
title: Oracle データベース アダプターを使用して BizTalk アプリケーションの開発 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Content-Based Routing (CBR)
- BizTalk orchestrations, using orchestrations to perform operations
ms.assetid: 65689c83-4a57-4aad-b0e9-f1bad901a7b9
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 05b342de0cb2bf7d99cf50774bedb81f36f82d9c
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37002363"
---
# <a name="develop-biztalk-applications-using-the-oracle-database-adapter"></a>Oracle データベース アダプターを使用して BizTalk アプリケーションを開発します。
BizTalk アプリケーションを開発する場合で BizTalk プロジェクトを作成する必要があります[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]を使用して、 [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)] XML スキーマを生成します。 スキーマが生成されると、コンテンツ ベースのルーティング (CBR) を使用するか、または、生成されたスキーマに準拠するメッセージを送受信する BizTalk オーケストレーションを作成することができます。  
  
 CBR は、場所、Oracle データベースに送信されるメッセージには、処理を要する処理は不要のシナリオで使用できます。 たとえば、受信ポートが特定の型だけのメッセージを受信することがわかっている場合は、送信ポートにフィルター式に一致するメッセージをルーティングする送信ポートにフィルターを追加できます。  
  
 、BizTalk オーケストレーションの送信を作成およびとの間でメッセージを送受信する受信ポート、 [!INCLUDE[wcfadapter_short](../../includes/wcfadapter-short-md.md)]、さらに、メッセージを送信する[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]します。 このセクションでは、BizTalk オーケストレーションを使用して、使用して Oracle データベースで操作を実行する方法の情報を提供します。、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]します。 [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]順番に使用して、 [!INCLUDE[wcfadapter_short](../../includes/wcfadapter-short-md.md)]、WCF バインドと対話することができます。  
  
> [!IMPORTANT]
>  使用する、 [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] microsoft [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]、常に設定する必要があります、 **EnableBizTalkCompatibilityMode**プロパティをバインド**True**します。 バインドのプロパティを設定する方法については、次を参照してください。 [for Oracle Database バインド プロパティを構成する](../../adapters-and-accelerators/adapter-oracle-database/configure-the-binding-properties-for-oracle-database.md)します。  
> 
> [!IMPORTANT]
>  [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]に含まれている[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]は、BizTalk Server 管理コンソールに表示されません。 アダプター、[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]は WCF ベースし、WCF カスタム バインドを使用します。 BizTalk Server 管理コンソールに表示されます、[!INCLUDE[wcfadapter_short](../../includes/wcfadapter-short-md.md)]します。 自動的に表示、WCF カスタム バインドされ、WCF ベースに表示されませんが、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]します。  
> 
> また、使用してメタデータを生成する、[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]します。 使用しないでください、[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]します。 使用方法について、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]を参照してください[Visual Studio での Oracle データベース操作のメタデータを取得](../../adapters-and-accelerators/adapter-oracle-database/get-metadata-for-oracle-database-operations-in-visual-studio.md)します。 
> 
> その他のアダプター バージョン間違いでは、次を参照してください。[を移行する BizTalk プロジェクト作成を使用して BizTalk ODBC Adapter for Oracle Database](http://msdn.microsoft.com/library/18f40265-c7f3-44a1-99b6-1b1dc800561e)します。  
  
  
  
## <a name="see-also"></a>参照  
[Oracle データベース アプリケーションの開発](../../adapters-and-accelerators/adapter-oracle-database/develop-your-oracle-database-applications.md)