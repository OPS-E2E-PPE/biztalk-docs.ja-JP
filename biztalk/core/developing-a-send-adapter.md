---
title: 送信アダプターの開発 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 11b430da-ddba-4827-b9a1-c61338b9c647
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6909d181b2dbc76597b1e091e0a1a9cf0beaea9f
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65389669"
---
# <a name="developing-a-send-adapter"></a><span data-ttu-id="683d7-102">送信アダプターの開発</span><span class="sxs-lookup"><span data-stu-id="683d7-102">Developing a Send Adapter</span></span>
<span data-ttu-id="683d7-103">ここでは、送信アダプター内で発生するオブジェクト間の対話処理について説明します。</span><span class="sxs-lookup"><span data-stu-id="683d7-103">This section describes the object interactions that occur within send adapters.</span></span> <span data-ttu-id="683d7-104">この情報は、送信アダプターの作成時にカスタム アダプター開発の指針としたり、ネイティブ アダプターの機能を理解するうえで役立ちます。</span><span class="sxs-lookup"><span data-stu-id="683d7-104">You can use this information to guide custom adapter development when creating send adapters, or to learn about how the native adapters work.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="683d7-105">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="683d7-105">In This Section</span></span>  
  
-   [<span data-ttu-id="683d7-106">送信アダプターの交換パターン</span><span class="sxs-lookup"><span data-stu-id="683d7-106">Exchange Patterns for Send Adapters</span></span>](../core/exchange-patterns-for-send-adapters.md)  
  
-   [<span data-ttu-id="683d7-107">送信アダプターのインスタンス化と初期化</span><span class="sxs-lookup"><span data-stu-id="683d7-107">Instantiating and Initializing a Send Adapter</span></span>](../core/instantiating-and-initializing-a-send-adapter.md)  
  
-   [<span data-ttu-id="683d7-108">送信アダプターの操作</span><span class="sxs-lookup"><span data-stu-id="683d7-108">Send Adapter Operations</span></span>](../core/send-adapter-operations.md)  
  
-   [<span data-ttu-id="683d7-109">送信処理用メッセージのバッチ処理</span><span class="sxs-lookup"><span data-stu-id="683d7-109">Batching Messages for Send Processing</span></span>](../core/batching-messages-for-send-processing.md)  
  
-   [<span data-ttu-id="683d7-110">送信アダプター用のインターフェイス</span><span class="sxs-lookup"><span data-stu-id="683d7-110">Interfaces for Send Adapters</span></span>](../core/interfaces-for-send-adapters.md)  
  
-   [<span data-ttu-id="683d7-111">送信アダプター用の SSO サポート</span><span class="sxs-lookup"><span data-stu-id="683d7-111">SSO Support for Send Adapters</span></span>](../core/sso-support-for-send-adapters.md)