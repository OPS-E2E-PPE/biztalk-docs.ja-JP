---
title: "GetContextProperty2 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 2554a210-cfb4-4b63-9afa-ffe2a853ba7b
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f834bf1271f6706c332123d8b1835e0bd730f069
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="getcontextproperty"></a><span data-ttu-id="c0a10-102">GetContextProperty</span><span class="sxs-lookup"><span data-stu-id="c0a10-102">GetContextProperty</span></span>
<span data-ttu-id="c0a10-103">要求されたコンテキスト プロパティをスタックにプッシュします。</span><span class="sxs-lookup"><span data-stu-id="c0a10-103">Pushes the requested context property onto the stack.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c0a10-104">構文</span><span class="sxs-lookup"><span data-stu-id="c0a10-104">Syntax</span></span>  
  
```  
  
<wf:Operation Name="GetContextProperty">  
  <wf:Argument>ContextPropertyName</wf:Argument>  
</wf:Operation>  
```  
  
#### <a name="parameters"></a><span data-ttu-id="c0a10-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="c0a10-105">Parameters</span></span>  
 <span data-ttu-id="c0a10-106">次のコンテキスト プロパティ名のいずれかを指定します。</span><span class="sxs-lookup"><span data-stu-id="c0a10-106">One of the following context property names:</span></span>  
  
|<span data-ttu-id="c0a10-107">コンテキスト プロパティ名</span><span class="sxs-lookup"><span data-stu-id="c0a10-107">Context property name</span></span>|<span data-ttu-id="c0a10-108">Description</span><span class="sxs-lookup"><span data-stu-id="c0a10-108">Description</span></span>|  
|---------------------------|-----------------|  
|<span data-ttu-id="c0a10-109">EventTime</span><span class="sxs-lookup"><span data-stu-id="c0a10-109">EventTime</span></span>|<span data-ttu-id="c0a10-110">現在の日付と時刻です。</span><span class="sxs-lookup"><span data-stu-id="c0a10-110">Current date and time.</span></span>|  
|<span data-ttu-id="c0a10-111">InstanceId</span><span class="sxs-lookup"><span data-stu-id="c0a10-111">InstanceId</span></span>|<span data-ttu-id="c0a10-112">ワークフロー インスタンスの ID です。</span><span class="sxs-lookup"><span data-stu-id="c0a10-112">Workflow instance ID.</span></span>|  
  
> [!NOTE]
>  <span data-ttu-id="c0a10-113">コンテキスト プロパティ名は大文字と小文字が区別されます。</span><span class="sxs-lookup"><span data-stu-id="c0a10-113">The context property names are case-sensitive.</span></span>  
  
## <a name="pushed-value"></a><span data-ttu-id="c0a10-114">プッシュされた値</span><span class="sxs-lookup"><span data-stu-id="c0a10-114">Pushed Value</span></span>  
 <span data-ttu-id="c0a10-115">要求されたコンテキスト プロパティを表す文字列です。</span><span class="sxs-lookup"><span data-stu-id="c0a10-115">String containing the requested context property.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c0a10-116">解説</span><span class="sxs-lookup"><span data-stu-id="c0a10-116">Remarks</span></span>  
 <span data-ttu-id="c0a10-117">時刻は UTC 形式でデータベース内部に格納されます。</span><span class="sxs-lookup"><span data-stu-id="c0a10-117">Time is stored in UTC format inside of the database.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c0a10-118">例</span><span class="sxs-lookup"><span data-stu-id="c0a10-118">Example</span></span>  
 <span data-ttu-id="c0a10-119">次の例では、式をプルするために、 **InstanceId**相関 ID を設定する correlationID ブロックの内部で使用します。</span><span class="sxs-lookup"><span data-stu-id="c0a10-119">In the following sample, an expression for pulling the **InstanceId** is used inside of a correlationID block to set the correlation ID.</span></span>  
  
```  
<ic:CorrelationID>  
  <ic:Expression>  
    <wf:Operation Name="GetContextProperty">  
      <wf:Argument>InstanceId</wf:Argument>  
    </wf:Operation>  
  </ic:Expression>  
</ic:CorrelationID>  
```  
  
 <span data-ttu-id="c0a10-120">これは `GetContextProperty` の一般的な使用方法です。</span><span class="sxs-lookup"><span data-stu-id="c0a10-120">This is a common use of `GetContextProperty`.</span></span>