---
title: "付録 a: コンポーネント インターフェイスのメソッド |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- component interfaces, methods
- methods, component interfaces
- component interface methods
ms.assetid: c8377589-fbdf-4287-b822-53263a00381d
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 61cb5b87cb063f22c889291b8eff3b2be50d64a7
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="appendix-a-component-interface-methods"></a><span data-ttu-id="09781-102">付録 a: コンポーネント インターフェイス メソッド</span><span class="sxs-lookup"><span data-stu-id="09781-102">Appendix A: Component Interface Methods</span></span>
<span data-ttu-id="09781-103">Microsoft BizTalk Adapter for PeopleSoft Enterprise は、コンポーネント インターフェイスの標準的なメソッドを提供します。</span><span class="sxs-lookup"><span data-stu-id="09781-103">Microsoft BizTalk Adapter for PeopleSoft Enterprise provides standard methods for component interfaces.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="09781-104">これらのメソッドの Ex バージョンで使用される `interactiveMode` パラメーターは、バックエンドに対する呼び出しのデバッグを補助します (`Create/CreateEx`、`Update/UpdateEx`、および `DeleteOnly`)。</span><span class="sxs-lookup"><span data-stu-id="09781-104">The `interactiveMode` parameter, in the Ex-version of the methods, assists in debugging a call to the back-end (`Create/CreateEx`, `Update/UpdateEx`, and `DeleteOnly`).</span></span> <span data-ttu-id="09781-105">内の各項目、* Ex、バックエンドの呼び出しと呼ばれるとは別に、どの項目が失敗しましただけを認識できるようにします。</span><span class="sxs-lookup"><span data-stu-id="09781-105">Each item in the *Ex call to the back-end is called separately, so you know exactly which item failed.</span></span> <span data-ttu-id="09781-106">使用するときにパフォーマンスの低下がある、 \*Ex メソッドの各プロパティの項目が別個の呼び出しを受信するためです。</span><span class="sxs-lookup"><span data-stu-id="09781-106">There is a decrease in performance when you use an \*Ex method because each property's item receives a separate call.</span></span> <span data-ttu-id="09781-107">開発できる\*Ex メソッドしに切り替えると、メイン メソッド (たとえば、 `Create`) 運用環境用です。</span><span class="sxs-lookup"><span data-stu-id="09781-107">You can develop with \*Ex method and then switch to the main method (for example, `Create`) for production.</span></span> <span data-ttu-id="09781-108">メソッドの使用を切り替える、実稼働環境にデバッグ スイッチを使用することもでき、 \*Ex メソッドです。</span><span class="sxs-lookup"><span data-stu-id="09781-108">You can also use a debug switch at production to switch between using the method and the \*Ex method.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="09781-109">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="09781-109">In This Section</span></span>  
  
-   [<span data-ttu-id="09781-110">CreateEx メソッド</span><span class="sxs-lookup"><span data-stu-id="09781-110">CreateEx Method</span></span>](../core/createex-method.md)  
  
-   [<span data-ttu-id="09781-111">DeleteOnly メソッド</span><span class="sxs-lookup"><span data-stu-id="09781-111">DeleteOnly Method</span></span>](../core/deleteonly-method.md)  
  
-   [<span data-ttu-id="09781-112">Find メソッド</span><span class="sxs-lookup"><span data-stu-id="09781-112">Find Method</span></span>](../core/find-method.md)  
  
-   [<span data-ttu-id="09781-113">Get メソッド</span><span class="sxs-lookup"><span data-stu-id="09781-113">Get Method</span></span>](../core/get-method.md)  
  
-   [<span data-ttu-id="09781-114">UpdateEx メソッド</span><span class="sxs-lookup"><span data-stu-id="09781-114">UpdateEx Method</span></span>](../core/updateex-method.md)  
  
-   [<span data-ttu-id="09781-115">コンポーネント インターフェイス ユーザー定義メソッド</span><span class="sxs-lookup"><span data-stu-id="09781-115">Component Interface User-Defined Methods</span></span>](../core/component-interface-user-defined-methods.md)  
  
-   [<span data-ttu-id="09781-116">発効日のプロパティ</span><span class="sxs-lookup"><span data-stu-id="09781-116">Effective Date Properties</span></span>](../core/effective-date-properties.md)