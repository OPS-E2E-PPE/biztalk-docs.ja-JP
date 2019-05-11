---
title: フォールト Message1 を追加する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- exceptions, adding messages
- fault messages, adding
- adding, fault messages
- faults, adding messages
ms.assetid: 9d21de6b-c1a5-46e9-a9dc-d6aa7b5fe34b
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ed9bcaab8db10ee0be664b02028af9b9a79981d3
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65343845"
---
# <a name="how-to-add-a-fault-message"></a><span data-ttu-id="d0dd1-102">エラー メッセージを追加する方法</span><span class="sxs-lookup"><span data-stu-id="d0dd1-102">How to Add a Fault Message</span></span>
<span data-ttu-id="d0dd1-103">最初に、バックエンド システムへのポートを作成したときに、要求と応答が含まれています。</span><span class="sxs-lookup"><span data-stu-id="d0dd1-103">When you first created the port to the back-end system, it contained a request and a response.</span></span> <span data-ttu-id="d0dd1-104">例外をキャプチャするエラーを追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d0dd1-104">You must add a fault to capture the exception.</span></span>  
  
### <a name="to-add-a-fault-message"></a><span data-ttu-id="d0dd1-105">エラー メッセージを追加するには</span><span class="sxs-lookup"><span data-stu-id="d0dd1-105">To add a fault message</span></span>  
  
1.  <span data-ttu-id="d0dd1-106">右クリック**ポート操作**を選び、**新しいエラー メッセージ**します。</span><span class="sxs-lookup"><span data-stu-id="d0dd1-106">Right-click **Port Operation**, and then select a **New Fault Message**.</span></span>  
  
     <span data-ttu-id="d0dd1-107">A**フォールト**下に表示されます、**要求と応答**ポート。</span><span class="sxs-lookup"><span data-stu-id="d0dd1-107">A **Fault** appears under the **Request and Response** in the port.</span></span>  
  
2.  <span data-ttu-id="d0dd1-108">**オーケストレーション**画面を右クリックして**メッセージ**、し、**新しいメッセージ**。</span><span class="sxs-lookup"><span data-stu-id="d0dd1-108">On the **Orchestration View** screen, right-click **Messages**, and then select **New Message**.</span></span>  
  
     <span data-ttu-id="d0dd1-109">これには、エラーに割り当てることができる Message_3 が作成されます。</span><span class="sxs-lookup"><span data-stu-id="d0dd1-109">This creates Message_3, which you can assign specifically to the fault.</span></span>  
  
3.  <span data-ttu-id="d0dd1-110">右クリックして**Message_3**にアクセスする、**プロパティ**ウィンドウ。</span><span class="sxs-lookup"><span data-stu-id="d0dd1-110">Right-click **Message_3** to access the **Properties** window.</span></span>  
  
    1.  <span data-ttu-id="d0dd1-111">設定、**メッセージの種類**します。</span><span class="sxs-lookup"><span data-stu-id="d0dd1-111">Set the **Message Type**.</span></span>  
  
    2.  <span data-ttu-id="d0dd1-112">選択**スキーマ**から選び**ref アセンブリ**します。</span><span class="sxs-lookup"><span data-stu-id="d0dd1-112">Select **Schema**, and then select from **ref assembly**.</span></span>  
  
         <span data-ttu-id="d0dd1-113">開き、**成果物の種類の選択**ウィンドウ。</span><span class="sxs-lookup"><span data-stu-id="d0dd1-113">This opens a **Select Artifact Type** window.</span></span>  
  
    3.  <span data-ttu-id="d0dd1-114">下へスクロールし、完全修飾エラーを選択します。</span><span class="sxs-lookup"><span data-stu-id="d0dd1-114">Scroll down and select the fully qualified fault.</span></span>  
  
         <span data-ttu-id="d0dd1-115">名前は**BTS します。SOAP_Envelope_1__1.fault**します。</span><span class="sxs-lookup"><span data-stu-id="d0dd1-115">The name is **BTS.SOAP_Envelope_1__1.fault**.</span></span> <span data-ttu-id="d0dd1-116">クリックして**OK**選択を確定し、ウィンドウを閉じます。</span><span class="sxs-lookup"><span data-stu-id="d0dd1-116">Click **OK** to accept the selection and close the window.</span></span>  
  
4.  <span data-ttu-id="d0dd1-117">右クリックし、**フォールト**にアクセスする、**プロパティ**ウィンドウ。</span><span class="sxs-lookup"><span data-stu-id="d0dd1-117">Right-click the **Fault** to access the **Properties** window.</span></span>  
  
    1.  <span data-ttu-id="d0dd1-118">設定、**メッセージの種類**します。</span><span class="sxs-lookup"><span data-stu-id="d0dd1-118">Set the **Message Type**.</span></span>  
  
    2.  <span data-ttu-id="d0dd1-119">選択**スキーマ**から選び**ref**アセンブリ。</span><span class="sxs-lookup"><span data-stu-id="d0dd1-119">Select **Schema** and then select from **ref** assembly.</span></span>  
  
         <span data-ttu-id="d0dd1-120">開き、**成果物の種類の選択**ウィンドウ。</span><span class="sxs-lookup"><span data-stu-id="d0dd1-120">This opens a **Select Artifact Type** window.</span></span>  
  
    3.  <span data-ttu-id="d0dd1-121">下へスクロールし、完全修飾エラーを選択します。</span><span class="sxs-lookup"><span data-stu-id="d0dd1-121">Scroll down and select the fully qualified fault.</span></span>  
  
         <span data-ttu-id="d0dd1-122">名前は**BTS します。SOAP_Envelope_1__1.fault**します。</span><span class="sxs-lookup"><span data-stu-id="d0dd1-122">The name is **BTS.SOAP_Envelope_1__1.fault**.</span></span>  
  
    4.  <span data-ttu-id="d0dd1-123">クリックして**OK**選択を確定し、ウィンドウを閉じます。</span><span class="sxs-lookup"><span data-stu-id="d0dd1-123">Click **OK** to accept the selection and close the window.</span></span>  
  
         <span data-ttu-id="d0dd1-124">![](../core/media/siebeladapter-17-exceptionhandling-addscope.gif "SiebelAdapter_17_ExceptionHandling_AddScope")</span><span class="sxs-lookup"><span data-stu-id="d0dd1-124">![](../core/media/siebeladapter-17-exceptionhandling-addscope.gif "SiebelAdapter_17_ExceptionHandling_AddScope")</span></span>  
  
5.  <span data-ttu-id="d0dd1-125">エラーの名前を付けた後 CatchException の例外オブジェクト型にこの名前を設定します。</span><span class="sxs-lookup"><span data-stu-id="d0dd1-125">After the fault is named, you will set this name to the CatchException's exception object type.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d0dd1-126">参照</span><span class="sxs-lookup"><span data-stu-id="d0dd1-126">See Also</span></span>  
 [<span data-ttu-id="d0dd1-127">BizTalk Server 例外処理の使用</span><span class="sxs-lookup"><span data-stu-id="d0dd1-127">Using BizTalk Server Exception Handling</span></span>](../core/using-biztalk-server-exception-handling2.md)