---
title: Siebel アダプターを使用して BizTalk アプリケーションを開発 |Microsoft ドキュメント
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
ms.openlocfilehash: c8267c07027d9994b0115ebaf49fde96e76f2716
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22221930"
---
# <a name="develop-biztalk-applications-using-the-siebel-adapter"></a>Siebel アダプターを使用して BizTalk アプリケーションを開発します。

## <a name="overview"></a>概要
BizTalk アプリケーションの開発で BizTalk プロジェクトを作成する[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]を使用して、 [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)] XML スキーマを生成します。 スキーマが生成されると、コンテンツ ベースのルーティング (CBR) を使用するか、生成されたスキーマに準拠するメッセージを送受信する BizTalk オーケストレーションを作成します。  
  
 CBR は、ここで、Siebel システムに送信されるメッセージには、処理を要する処理は不要のシナリオで使用できます。 たとえば、受信ポートが特定の型だけのメッセージを受信することがわかっている場合は、送信ポートにフィルター式と一致するメッセージをルーティングする送信ポートにフィルターを追加できます。  
  
 、BizTalk オーケストレーションの送信を作成およびとの間でメッセージを送受信する受信ポート、 [!INCLUDE[wcfadapter_short](../../includes/wcfadapter-short-md.md)]、さらに、メッセージを送信する[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]です。 このセクションで説明している Siebel システムでの操作を実行する BizTalk オーケストレーションの使用について、[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]です。 [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]順番に使用して、 [!INCLUDE[wcfadapter_short](../../includes/wcfadapter-short-md.md)] WCF バインドと対話することができます。  

## <a name="before-you-begin"></a>アンインストールの準備  

* 使用する、 [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] microsoft [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]、常に設定されて、 **EnableBizTalkCompatibilityMode**にプロパティのバインド**True**です。 手順については、次を参照してください。 [Siebel のバインドのプロパティを構成する](../../adapters-and-accelerators/adapter-siebel/configure-the-binding-properties-for-siebel.md)です。
  
* [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]付属[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]BizTalk Server 管理コンソールには自動的に表示されません。 これは、ため、 [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] WCF カスタム バインドは、します。 

* メタデータを生成するには、使用、[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]です。 使用しないで、[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]です。 使用方法について、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]を参照してください[Siebel 操作の Visual Studio でのメタデータを取得](../../adapters-and-accelerators/adapter-siebel/get-metadata-for-siebel-operations-in-visual-studio.md)です。   

  
## <a name="see-also"></a>参照  
[Siebel アプリケーションを開発します。](../../adapters-and-accelerators/adapter-siebel/develop-your-siebel-applications.md)