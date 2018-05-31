---
title: エラー メッセージを作成およびパブリッシュ |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: cc7ba1d9-b647-4cba-a3dc-4400505ff51f
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 57833cefedcf53b7355c17cf97d429d2eb988819
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22290682"
---
# <a name="creating-and-publishing-fault-messages"></a><span data-ttu-id="67d0e-102">作成、およびエラー メッセージの公開</span><span class="sxs-lookup"><span data-stu-id="67d0e-102">Creating and Publishing Fault Messages</span></span>
<span data-ttu-id="67d0e-103">例外管理フレームワークの機能を使用して例外を管理する方法を理解するためは、ここでは、ESB アプリケーションへのメッセージの送信に基づいた一般的なシナリオを示します。</span><span class="sxs-lookup"><span data-stu-id="67d0e-103">To help you understand how to use the features of the Exception Management Framework to manage exceptions, this section presents a common scenario based on the submission of a message to an ESB application.</span></span>  
  
 <span data-ttu-id="67d0e-104">システムへの請求書を送信してユーザーのシナリオで構成されます。</span><span class="sxs-lookup"><span data-stu-id="67d0e-104">The scenario consists of a user submitting an invoice to the system.</span></span> <span data-ttu-id="67d0e-105">オーケストレーションで請求書を処理中に、BizTalk ビジネス ルール エンジンは、データの一部が正しくないため、アプリケーション例外をスローします。</span><span class="sxs-lookup"><span data-stu-id="67d0e-105">During the course of processing the invoice in an orchestration, the BizTalk Business Rules Engine throws an application exception because some part of the data is incorrect.</span></span> <span data-ttu-id="67d0e-106">ビジネス プロセスは、例外をキャッチ、他人や他のことができます、メッセージを解決しを再送信メッセージを処理するシステムに害のあるメッセージを送信する必要があります。</span><span class="sxs-lookup"><span data-stu-id="67d0e-106">The business process should catch the exception, send the offending message to another person or system that can correct the message, and then resubmit the message for processing.</span></span>  
  
 <span data-ttu-id="67d0e-107">ESB 失敗オーケストレーション例外ルーティング機能を使用して、プロセスの手順は次に示します。</span><span class="sxs-lookup"><span data-stu-id="67d0e-107">When using the ESB Failed Orchestration Exception Routing feature, the process steps are the following:</span></span>  
  
1.  <span data-ttu-id="67d0e-108">例外ハンドラーでコードがエラーを検出し、呼び出すことによって、エラー メッセージを作成、 **CreateFaultMessage**メソッドを次のコード例に示すようにします。</span><span class="sxs-lookup"><span data-stu-id="67d0e-108">Code in the exception handler detects the error and creates a fault message by calling the **CreateFaultMessage** method, as shown in the following code example.</span></span>  
  
    ```csharp  
    // Create fault exception message.  
    faultMsg = Microsoft.Practices.ESB.ExceptionHandling.ExceptionMgmt.CreateFaultMessage();  
    ```  
  
2.  <span data-ttu-id="67d0e-109">ESB 例外処理機構では、フォールト メッセージ コンテキストに、エラーの説明を自動的に挿入 (たとえば、「ビジネス ルール エンジンがスローされました除算 0 による LoanProcessing ポリシーの処理中に。」) です。</span><span class="sxs-lookup"><span data-stu-id="67d0e-109">The ESB Exception mechanism automatically inserts the error description into the fault message context (for example, "The Business Rules Engine threw a divide by zero error while processing the LoanProcessing policy.").</span></span>  
  
3.  <span data-ttu-id="67d0e-110">ESB 例外処理機構は自動的にフォールト メッセージ コンテキストにエラーに固有のプロパティとアプリケーション固有のプロパティを昇格し、現在の環境から値を設定します。</span><span class="sxs-lookup"><span data-stu-id="67d0e-110">The ESB Exception mechanism automatically promotes failure-specific properties and application-specific properties into the fault message context and sets the values from the current environment.</span></span> <span data-ttu-id="67d0e-111">これらのプロパティは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="67d0e-111">These properties are the following:</span></span>  
  
    -   <span data-ttu-id="67d0e-112">**アプリケーション**(自動的に入力されます)</span><span class="sxs-lookup"><span data-stu-id="67d0e-112">**Application** (auto-populated)</span></span>  
  
    -   <span data-ttu-id="67d0e-113">**DateTime** (自動設定された UTC 値として)</span><span class="sxs-lookup"><span data-stu-id="67d0e-113">**DateTime** (auto-populated as a UTC value)</span></span>  
  
    -   <span data-ttu-id="67d0e-114">**説明**(自動設定された-例外メッセージ)</span><span class="sxs-lookup"><span data-stu-id="67d0e-114">**Description** (auto-populated—the exception message)</span></span>  
  
    -   <span data-ttu-id="67d0e-115">**ErrorType** (自動設定された、例外の種類)</span><span class="sxs-lookup"><span data-stu-id="67d0e-115">**ErrorType** (auto-populated—the exception type)</span></span>  
  
    -   <span data-ttu-id="67d0e-116">**MachineName** (自動設定された、現在のサーバー名)</span><span class="sxs-lookup"><span data-stu-id="67d0e-116">**MachineName** (auto-populated—the current server name)</span></span>  
  
    -   <span data-ttu-id="67d0e-117">**スコープ**(自動設定された、現在の例外ハンドラーを含むスコープ図形)</span><span class="sxs-lookup"><span data-stu-id="67d0e-117">**Scope** (auto-populated—the Scope shape that contains the current exception handler)</span></span>  
  
    -   <span data-ttu-id="67d0e-118">**ServiceName** (自動設定された、オーケストレーション名)</span><span class="sxs-lookup"><span data-stu-id="67d0e-118">**ServiceName** (auto-populated—the orchestration name)</span></span>  
  
    -   <span data-ttu-id="67d0e-119">**ServiceInstanceID**(自動設定された —、オーケストレーション インスタンス ID を GUID として)</span><span class="sxs-lookup"><span data-stu-id="67d0e-119">**ServiceInstanceID**(auto-populated—the orchestration instance ID as a GUID)</span></span>  
  
4.  <span data-ttu-id="67d0e-120">例外ハンドラーのコードは、次のコード例に示すように、必要に応じて、エラー メッセージの他のプロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="67d0e-120">Code in the exception handler sets other properties of the fault message as required, as shown in the following code example.</span></span>  
  
    ```csharp  
    // Set fault message properties.  
    faultMsg.Body.FailureCategory = "MessageBuild";  
    faultMsg.Body.FaultCode = 1000;  
    faultMsg.Body.FaultDescription = "Some error occurred";  
    faultMsg.Body.FaultSeverity =  
       Microsoft.Practices.ESB.ExceptionHandling.FaultSeverity.Severe;  
    ```  
  
5.  <span data-ttu-id="67d0e-121">ESB 例外処理機構は、現在を自動的にシリアル化**例外**オブジェクト、エラー メッセージにします。</span><span class="sxs-lookup"><span data-stu-id="67d0e-121">The ESB Exception mechanism automatically serializes the current **Exception** object into the fault message.</span></span>  
  
6.  <span data-ttu-id="67d0e-122">必要に応じて、例外ハンドラーのコードは現在のオーケストレーション メッセージの ESB フォールト メッセージを使用して、追加できます、 **AddMessage (faultMsg、messageToAdd)** メソッドです。</span><span class="sxs-lookup"><span data-stu-id="67d0e-122">Optionally, code in the exception handler can add current orchestration messages to the ESB fault message using the **AddMessage(faultMsg, messageToAdd)** method.</span></span> <span data-ttu-id="67d0e-123">このメソッドは、シリアル化し、次のコード例に示すように、すべてのコンテキスト プロパティを含むメッセージが引き続き発生します。</span><span class="sxs-lookup"><span data-stu-id="67d0e-123">This method serializes and persists the message, including all the context properties, as shown in the following code example.</span></span>  
  
    ```csharp  
    // Add other current orchestration messages to the fault message.  
    Microsoft.Practices.ESB.ExceptionHandling.ExceptionMgmt.AddMessage(  
                                faultMsg, approvedRequestMsg);  
    Microsoft.Practices.ESB.ExceptionHandling.ExceptionMgmt.AddMessage(  
                                faultMsg, DeniedRequestMsg, @"c:\temp");  
    ```  
  
7.  <span data-ttu-id="67d0e-124">例外ハンドラーのコードでは、直接バインド ポートを使用してメッセージ ボックス データベースに ESB フォールト メッセージを発行します。</span><span class="sxs-lookup"><span data-stu-id="67d0e-124">Code in the exception handler publishes the ESB fault message to the Message Box database using a direct bound port.</span></span>  
  
8.  <span data-ttu-id="67d0e-125">公開が成功すると、次のイベントが発生します。</span><span class="sxs-lookup"><span data-stu-id="67d0e-125">If publishing succeeds, the following events occur:</span></span>  
  
    -   <span data-ttu-id="67d0e-126">オーケストレーションまたは送信ポートのサブスクリプションでは、ESB フォールト メッセージを処理でき、そのコンテキスト プロパティの値を持つ完全な任意の追加メッセージを抽出することができます。</span><span class="sxs-lookup"><span data-stu-id="67d0e-126">Orchestration or send port subscriptions can process the ESB fault message and extract any added messages, complete with their context property values.</span></span>  
  
    -   <span data-ttu-id="67d0e-127">グローバル例外ハンドラー (送信ポート) は、ESB の管理ポータルを ESB フォールト メッセージを自動的に公開します。</span><span class="sxs-lookup"><span data-stu-id="67d0e-127">A global exception handler (a send port) automatically publishes the ESB fault message to the ESB Management Portal.</span></span>