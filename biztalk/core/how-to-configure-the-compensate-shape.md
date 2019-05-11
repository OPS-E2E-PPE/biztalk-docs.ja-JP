---
title: 補正図形を構成する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Compensate shape [Orchestration Designer], about Compensate shape
- Compensate shape [Orchestration Designer]
- compensations, Compensate shape [Orchestration Designer]
- configuring [Orchestration Designer], Compensate shape
- Compensate shape [Orchestration Designer], configuring
ms.assetid: 9f06289e-4d11-4864-9851-c210276865a7
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e04ffee84b47a6a4e5520ece823575b030ccd6ba
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65341018"
---
# <a name="how-to-configure-the-compensate-shape"></a><span data-ttu-id="3ab44-102">補正図形を構成する方法</span><span class="sxs-lookup"><span data-stu-id="3ab44-102">How to Configure the Compensate Shape</span></span>
<span data-ttu-id="3ab44-103">追加できるかどうか、オーケストレーションで入れ子になったトランザクションを使っている場合、**補正**補正ブロックまたはトランザクション スコープの例外ブロックに図形。</span><span class="sxs-lookup"><span data-stu-id="3ab44-103">If you are using nested transactions in your orchestration, you can add a **Compensate** shape in the compensation block or an exception block of a transaction scope.</span></span> <span data-ttu-id="3ab44-104">これにより、オーケストレーションを明示的に補正を入れ子になったトランザクションを実行できます。</span><span class="sxs-lookup"><span data-stu-id="3ab44-104">This enables your orchestration to explicitly perform compensation on a nested transaction.</span></span> <span data-ttu-id="3ab44-105">補正するトランザクションを指定する、**補正**図形、および入れ子になったトランザクションの補正コードが動作する、正常にコミットされたトランザクションを提供します。</span><span class="sxs-lookup"><span data-stu-id="3ab44-105">You specify which transaction you would like to be compensated in the **Compensate** shape, and any compensation code in the nested transaction will be run, provided the transaction committed successfully.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="3ab44-106">**補正**プロパティは、トランザクション スコープの一意の識別子を参照; はスコープの名前を参照していません。</span><span class="sxs-lookup"><span data-stu-id="3ab44-106">The **Compensation** property refers to the unique identifier of the transaction scope; it does not refer to the name of the scope.</span></span>  
  
 <span data-ttu-id="3ab44-107">さらに追加する 1 つ以上の入れ子になったトランザクションを補正する場合は、**補正**トランザクションごとの図形。</span><span class="sxs-lookup"><span data-stu-id="3ab44-107">If you want to compensate more than one nested transaction, you add an additional **Compensate** shape for each transaction.</span></span>  
  
 <span data-ttu-id="3ab44-108">いいえ**補正**図形が必要なは、外側のトランザクションに他の補正コードがない場合は、入れ子になったトランザクションの補正コードを自動的に実行されます。</span><span class="sxs-lookup"><span data-stu-id="3ab44-108">No **Compensate** shape is necessary if there is no other compensation code in an outer transaction; the compensation code of any nested transactions will be run automatically.</span></span> <span data-ttu-id="3ab44-109">**補正**図形で入れ子になったトランザクションを補正するかどうかを決定することにより、プロセスを細かく制御できます。</span><span class="sxs-lookup"><span data-stu-id="3ab44-109">The **Compensate** shape gives you control over the process by allowing you to decide whether or not you want a nested transaction to be compensated.</span></span>  
  
### <a name="to-configure-a-compensate-shape"></a><span data-ttu-id="3ab44-110">補正図形を構成するには</span><span class="sxs-lookup"><span data-stu-id="3ab44-110">To configure a Compensate shape</span></span>  
  
-   <span data-ttu-id="3ab44-111">[プロパティ] ウィンドウから呼び出す補正ブロックを選択します。、**補正**ドロップダウン リスト。</span><span class="sxs-lookup"><span data-stu-id="3ab44-111">In the Properties window, select the compensation block to call from the **Compensation** drop-down list.</span></span>  
  
     <span data-ttu-id="3ab44-112">すべての現在のトランザクションと、現在のトランザクション直下の子トランザクションを含むトランザクション、補正可能がドロップダウン リストが表示されます。</span><span class="sxs-lookup"><span data-stu-id="3ab44-112">The drop-down list will display all of the transactions which can be compensated, which includes the current transaction and any immediate child transactions of the current transaction.</span></span> <span data-ttu-id="3ab44-113">予想されるトランザクションを表示されない場合は、トランザクションの関係が原因が考えられます。</span><span class="sxs-lookup"><span data-stu-id="3ab44-113">If you cannot see a transaction that you expect, it might be due to the relationship of the transactions.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="3ab44-114">トランザクションの本体内から現在のトランザクションを補正することはできません。</span><span class="sxs-lookup"><span data-stu-id="3ab44-114">You cannot compensate the current transaction from within the body of the transaction.</span></span>  <span data-ttu-id="3ab44-115">補正ブロックまたはトランザクションの例外ブロックからそれを補うことができます。</span><span class="sxs-lookup"><span data-stu-id="3ab44-115">You can compensate it from the compensation block or an exception block of the transaction.</span></span>  
  
     <span data-ttu-id="3ab44-116">(1 つである) 場合、既定のハンドラーが呼び出されることを表す、現在のトランザクションと明示的な補正ブロックではないを補正する場合。</span><span class="sxs-lookup"><span data-stu-id="3ab44-116">If you choose to compensate the current transaction, that means that the default handler will be invoked, and not an explicit compensation block (if there is one).</span></span> <span data-ttu-id="3ab44-117">これは、自動的に正常に完了した直接入れ子になったトランザクションを補正するためのメカニズムです。</span><span class="sxs-lookup"><span data-stu-id="3ab44-117">This is a mechanism for automatically compensating directly nested transactions that have completed successfully.</span></span>