---
title: '付録 A: コンポーネント インターフェイスのメソッド |Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- component interfaces, methods
- methods, component interfaces
- component interface methods
ms.assetid: c8377589-fbdf-4287-b822-53263a00381d
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 48487071e0c4099158a10b0a7cfb922ad8d75717
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65359608"
---
# <a name="appendix-a-component-interface-methods"></a><span data-ttu-id="8ca2c-102">付録 A: コンポーネント インターフェイス メソッド</span><span class="sxs-lookup"><span data-stu-id="8ca2c-102">Appendix A: Component Interface Methods</span></span>
<span data-ttu-id="8ca2c-103">Microsoft BizTalk Adapter for PeopleSoft Enterprise では、コンポーネント インターフェイスの標準的なメソッドを提供します。</span><span class="sxs-lookup"><span data-stu-id="8ca2c-103">Microsoft BizTalk Adapter for PeopleSoft Enterprise provides standard methods for component interfaces.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="8ca2c-104">`interactiveMode` 、メソッドの Ex バージョンで、パラメーター、バックエンドへの呼び出しのデバッグを支援します (`Create/CreateEx`、 `Update/UpdateEx`、および`DeleteOnly`)。</span><span class="sxs-lookup"><span data-stu-id="8ca2c-104">The `interactiveMode` parameter, in the Ex-version of the methods, assists in debugging a call to the back-end (`Create/CreateEx`, `Update/UpdateEx`, and `DeleteOnly`).</span></span> <span data-ttu-id="8ca2c-105">内の各項目、\*、バックエンドへの呼び出し例別に呼び出される、エラーを正確にどの項目を認識できるようにします。</span><span class="sxs-lookup"><span data-stu-id="8ca2c-105">Each item in the \*Ex call to the back-end is called separately, so you know exactly which item failed.</span></span> <span data-ttu-id="8ca2c-106">使用するときにパフォーマンスの低下がある、 \*Ex メソッド各プロパティのアイテムが別個の呼び出しを受け取るため。</span><span class="sxs-lookup"><span data-stu-id="8ca2c-106">There is a decrease in performance when you use an \*Ex method because each property's item receives a separate call.</span></span> <span data-ttu-id="8ca2c-107">開発できる\*Ex メソッドと main メソッドに次のスイッチ (たとえば、 `Create`) 運用環境の。</span><span class="sxs-lookup"><span data-stu-id="8ca2c-107">You can develop with \*Ex method and then switch to the main method (for example, `Create`) for production.</span></span> <span data-ttu-id="8ca2c-108">メソッドの使用を切り替える、運用環境でデバッグ スイッチを使用することもでき、 \*Ex メソッド。</span><span class="sxs-lookup"><span data-stu-id="8ca2c-108">You can also use a debug switch at production to switch between using the method and the \*Ex method.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="8ca2c-109">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="8ca2c-109">In This Section</span></span>  
  
-   [<span data-ttu-id="8ca2c-110">CreateEx メソッド</span><span class="sxs-lookup"><span data-stu-id="8ca2c-110">CreateEx Method</span></span>](../core/createex-method.md)  
  
-   [<span data-ttu-id="8ca2c-111">DeleteOnly メソッド</span><span class="sxs-lookup"><span data-stu-id="8ca2c-111">DeleteOnly Method</span></span>](../core/deleteonly-method.md)  
  
-   [<span data-ttu-id="8ca2c-112">Find メソッド</span><span class="sxs-lookup"><span data-stu-id="8ca2c-112">Find Method</span></span>](../core/find-method.md)  
  
-   [<span data-ttu-id="8ca2c-113">Get メソッド</span><span class="sxs-lookup"><span data-stu-id="8ca2c-113">Get Method</span></span>](../core/get-method.md)  
  
-   [<span data-ttu-id="8ca2c-114">UpdateEx メソッド</span><span class="sxs-lookup"><span data-stu-id="8ca2c-114">UpdateEx Method</span></span>](../core/updateex-method.md)  
  
-   [<span data-ttu-id="8ca2c-115">コンポーネント インターフェイス ユーザー定義メソッド</span><span class="sxs-lookup"><span data-stu-id="8ca2c-115">Component Interface User-Defined Methods</span></span>](../core/component-interface-user-defined-methods.md)  
  
-   [<span data-ttu-id="8ca2c-116">発効日のプロパティ</span><span class="sxs-lookup"><span data-stu-id="8ca2c-116">Effective Date Properties</span></span>](../core/effective-date-properties.md)