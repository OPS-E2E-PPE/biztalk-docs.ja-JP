---
title: Siebel アダプターを使用して BizTalk アプリケーションの開発 |Microsoft Docs
ms.custom: ''
ms.date: 08/02/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- BizTalk applications, developing
- developing, BizTalk applications
- CBR
- Content-Based Routing
ms.assetid: 1a2a9765-305c-44b2-aed7-5437725e4c19
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9302dca6a86cbc149a0fd5aa23acc844ff803ff8
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65371717"
---
# <a name="develop-biztalk-applications-using-the-siebel-adapter"></a>Siebel アダプターを使用して BizTalk アプリケーションを開発します。

## <a name="overview"></a>概要
BizTalk アプリケーションを開発する場合で BizTalk プロジェクトを作成する必要があります[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]を使用して、 [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)] XML スキーマを生成します。 スキーマが生成されると、コンテンツ ベースのルーティング (CBR) を使用するか、または、生成されたスキーマに準拠するメッセージを送受信する BizTalk オーケストレーションを作成することができます。  
  
 CBR は、場所、Siebel システムに送信されるメッセージには、処理を要する処理は不要のシナリオで使用できます。 たとえば、受信ポートが特定の型だけのメッセージを受信することがわかっている場合は、送信ポートにフィルター式に一致するメッセージをルーティングする送信ポートにフィルターを追加できます。  
  
 、BizTalk オーケストレーションの送信を作成およびとの間でメッセージを送受信する受信ポート、 [!INCLUDE[wcfadapter_short](../../includes/wcfadapter-short-md.md)]、さらに、メッセージを送信する[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]します。 このセクションを使用して Siebel システムの操作を実行する BizTalk オーケストレーションを使用する方法について説明します、[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]します。 [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]順番に使用して、 [!INCLUDE[wcfadapter_short](../../includes/wcfadapter-short-md.md)] WCF バインドと対話することができます。  

## <a name="before-you-begin"></a>アンインストールの準備  

* 使用する、 [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] microsoft [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]、常に設定されて、 **EnableBizTalkCompatibilityMode**プロパティをバインド**True**します。 手順については、次を参照してください。 [for Siebel のバインドのプロパティを構成する](../../adapters-and-accelerators/adapter-siebel/configure-the-binding-properties-for-siebel.md)します。
  
* [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]付属[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]は、BizTalk Server 管理コンソールに自動的に表示されません。 これは、ため、 [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] WCF カスタム バインドします。 

* メタデータを生成するには、使用、[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]します。 使用しないでください、[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]します。 使用方法について、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]を参照してください[Visual Studio で Siebel 操作のメタデータの取得](../../adapters-and-accelerators/adapter-siebel/get-metadata-for-siebel-operations-in-visual-studio.md)します。   

  
## <a name="see-also"></a>参照  
[Siebel アプリケーションの開発](../../adapters-and-accelerators/adapter-siebel/develop-your-siebel-applications.md)