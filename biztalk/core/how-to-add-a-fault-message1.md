---
title: フォールト Message1 を追加する方法 |Microsoft ドキュメント
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
ms.openlocfilehash: 87ef85460f6ca6aea046ef9efff60fd198664cd1
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22246650"
---
# <a name="how-to-add-a-fault-message"></a><span data-ttu-id="1d4fa-102">エラー メッセージを追加する方法</span><span class="sxs-lookup"><span data-stu-id="1d4fa-102">How to Add a Fault Message</span></span>
<span data-ttu-id="1d4fa-103">最初に作成したバックエンド システムへのポートには、要求と応答が含まれていました。</span><span class="sxs-lookup"><span data-stu-id="1d4fa-103">When you first created the port to the back-end system, it contained a request and a response.</span></span> <span data-ttu-id="1d4fa-104">例外を取得するには、これにエラーを追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1d4fa-104">You must add a fault to capture the exception.</span></span>  
  
### <a name="to-add-a-fault-message"></a><span data-ttu-id="1d4fa-105">エラー メッセージを追加するには</span><span class="sxs-lookup"><span data-stu-id="1d4fa-105">To add a fault message</span></span>  
  
1.  <span data-ttu-id="1d4fa-106">右クリック**ポート操作**、クリックして、**新しいエラー メッセージ**です。</span><span class="sxs-lookup"><span data-stu-id="1d4fa-106">Right-click **Port Operation**, and then select a **New Fault Message**.</span></span>  
  
     <span data-ttu-id="1d4fa-107">A**フォールト**下に表示されます、**要求と応答**ポートです。</span><span class="sxs-lookup"><span data-stu-id="1d4fa-107">A **Fault** appears under the **Request and Response** in the port.</span></span>  
  
2.  <span data-ttu-id="1d4fa-108">**オーケストレーション**画面を右クリックして**メッセージ**、し、**新しいメッセージ**です。</span><span class="sxs-lookup"><span data-stu-id="1d4fa-108">On the **Orchestration View** screen, right-click **Messages**, and then select **New Message**.</span></span>  
  
     <span data-ttu-id="1d4fa-109">これにより Message_3 が作成され、このエラーに割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="1d4fa-109">This creates Message_3, which you can assign specifically to the fault.</span></span>  
  
3.  <span data-ttu-id="1d4fa-110">右クリック**Message_3**にアクセスする、**プロパティ**ウィンドウです。</span><span class="sxs-lookup"><span data-stu-id="1d4fa-110">Right-click **Message_3** to access the **Properties** window.</span></span>  
  
    1.  <span data-ttu-id="1d4fa-111">設定、**メッセージの種類**です。</span><span class="sxs-lookup"><span data-stu-id="1d4fa-111">Set the **Message Type**.</span></span>  
  
    2.  <span data-ttu-id="1d4fa-112">選択**スキーマ**から順に選択および**ref アセンブリ**です。</span><span class="sxs-lookup"><span data-stu-id="1d4fa-112">Select **Schema**, and then select from **ref assembly**.</span></span>  
  
         <span data-ttu-id="1d4fa-113">開き、**成果物の種類の選択**ウィンドウです。</span><span class="sxs-lookup"><span data-stu-id="1d4fa-113">This opens a **Select Artifact Type** window.</span></span>  
  
    3.  <span data-ttu-id="1d4fa-114">画面をスクロールし、完全修飾エラーを選択します。</span><span class="sxs-lookup"><span data-stu-id="1d4fa-114">Scroll down and select the fully qualified fault.</span></span>  
  
         <span data-ttu-id="1d4fa-115">名前は**BTS です。SOAP_Envelope_1__1.fault**です。</span><span class="sxs-lookup"><span data-stu-id="1d4fa-115">The name is **BTS.SOAP_Envelope_1__1.fault**.</span></span> <span data-ttu-id="1d4fa-116">をクリックして**OK**選択を確定し、ウィンドウを閉じます。</span><span class="sxs-lookup"><span data-stu-id="1d4fa-116">Click **OK** to accept the selection and close the window.</span></span>  
  
4.  <span data-ttu-id="1d4fa-117">右クリックし、**フォールト**にアクセスする、**プロパティ**ウィンドウです。</span><span class="sxs-lookup"><span data-stu-id="1d4fa-117">Right-click the **Fault** to access the **Properties** window.</span></span>  
  
    1.  <span data-ttu-id="1d4fa-118">設定、**メッセージの種類**です。</span><span class="sxs-lookup"><span data-stu-id="1d4fa-118">Set the **Message Type**.</span></span>  
  
    2.  <span data-ttu-id="1d4fa-119">選択**スキーマ**から順に選択および**ref**アセンブリ。</span><span class="sxs-lookup"><span data-stu-id="1d4fa-119">Select **Schema** and then select from **ref** assembly.</span></span>  
  
         <span data-ttu-id="1d4fa-120">開き、**成果物の種類の選択**ウィンドウです。</span><span class="sxs-lookup"><span data-stu-id="1d4fa-120">This opens a **Select Artifact Type** window.</span></span>  
  
    3.  <span data-ttu-id="1d4fa-121">画面をスクロールし、完全修飾エラーを選択します。</span><span class="sxs-lookup"><span data-stu-id="1d4fa-121">Scroll down and select the fully qualified fault.</span></span>  
  
         <span data-ttu-id="1d4fa-122">名前は**BTS です。SOAP_Envelope_1__1.fault**です。</span><span class="sxs-lookup"><span data-stu-id="1d4fa-122">The name is **BTS.SOAP_Envelope_1__1.fault**.</span></span>  
  
    4.  <span data-ttu-id="1d4fa-123">をクリックして**OK**選択を確定し、ウィンドウを閉じます。</span><span class="sxs-lookup"><span data-stu-id="1d4fa-123">Click **OK** to accept the selection and close the window.</span></span>  
  
         ![](../core/media/siebeladapter-17-exceptionhandling-addscope.gif "SiebelAdapter_17_ExceptionHandling_AddScope")  
  
5.  <span data-ttu-id="1d4fa-124">エラーに名前を付けたら、この名前を CatchException の例外オブジェクト型に設定します。</span><span class="sxs-lookup"><span data-stu-id="1d4fa-124">After the fault is named, you will set this name to the CatchException's exception object type.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1d4fa-125">参照</span><span class="sxs-lookup"><span data-stu-id="1d4fa-125">See Also</span></span>  
 [<span data-ttu-id="1d4fa-126">BizTalk Server 例外処理の使用</span><span class="sxs-lookup"><span data-stu-id="1d4fa-126">Using BizTalk Server Exception Handling</span></span>](../core/using-biztalk-server-exception-handling2.md)