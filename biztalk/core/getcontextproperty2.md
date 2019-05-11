---
title: GetContextProperty2 | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2554a210-cfb4-4b63-9afa-ffe2a853ba7b
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ec2f155b9fdb1cf79419531cc7ec2d3e8b87c791
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65387699"
---
# <a name="getcontextproperty"></a><span data-ttu-id="b9336-102">GetContextProperty</span><span class="sxs-lookup"><span data-stu-id="b9336-102">GetContextProperty</span></span>
<span data-ttu-id="b9336-103">要求されたコンテキスト プロパティをスタックにプッシュします。</span><span class="sxs-lookup"><span data-stu-id="b9336-103">Pushes the requested context property onto the stack.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b9336-104">構文</span><span class="sxs-lookup"><span data-stu-id="b9336-104">Syntax</span></span>  
  
```  
  
<wf:Operation Name="GetContextProperty">  
  <wf:Argument>ContextPropertyName</wf:Argument>  
</wf:Operation>  
```  
  
#### <a name="parameters"></a><span data-ttu-id="b9336-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="b9336-105">Parameters</span></span>  
 <span data-ttu-id="b9336-106">次のコンテキスト プロパティ名のいずれかを指定します。</span><span class="sxs-lookup"><span data-stu-id="b9336-106">One of the following context property names:</span></span>  
  
|<span data-ttu-id="b9336-107">コンテキスト プロパティ名</span><span class="sxs-lookup"><span data-stu-id="b9336-107">Context property name</span></span>|<span data-ttu-id="b9336-108">説明</span><span class="sxs-lookup"><span data-stu-id="b9336-108">Description</span></span>|  
|---------------------------|-----------------|  
|<span data-ttu-id="b9336-109">EventTime</span><span class="sxs-lookup"><span data-stu-id="b9336-109">EventTime</span></span>|<span data-ttu-id="b9336-110">現在の日付と時刻です。</span><span class="sxs-lookup"><span data-stu-id="b9336-110">Current date and time.</span></span>|  
|<span data-ttu-id="b9336-111">InstanceId</span><span class="sxs-lookup"><span data-stu-id="b9336-111">InstanceId</span></span>|<span data-ttu-id="b9336-112">ワークフロー インスタンスの id。</span><span class="sxs-lookup"><span data-stu-id="b9336-112">Workflow instance ID.</span></span>|  
  
> [!NOTE]
>  <span data-ttu-id="b9336-113">コンテキスト プロパティ名は大文字と小文字が区別されます。</span><span class="sxs-lookup"><span data-stu-id="b9336-113">The context property names are case-sensitive.</span></span>  
  
## <a name="pushed-value"></a><span data-ttu-id="b9336-114">プッシュされた値</span><span class="sxs-lookup"><span data-stu-id="b9336-114">Pushed Value</span></span>  
 <span data-ttu-id="b9336-115">要求されたコンテキスト プロパティを表す文字列です。</span><span class="sxs-lookup"><span data-stu-id="b9336-115">String containing the requested context property.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b9336-116">コメント</span><span class="sxs-lookup"><span data-stu-id="b9336-116">Remarks</span></span>  
 <span data-ttu-id="b9336-117">時刻は UTC 形式でデータベース内部に格納されます。</span><span class="sxs-lookup"><span data-stu-id="b9336-117">Time is stored in UTC format inside of the database.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b9336-118">例</span><span class="sxs-lookup"><span data-stu-id="b9336-118">Example</span></span>  
 <span data-ttu-id="b9336-119">取得する式は、次の例で、 **InstanceId**相関 ID を設定する correlationID ブロックの内部で使用</span><span class="sxs-lookup"><span data-stu-id="b9336-119">In the following sample, an expression for pulling the **InstanceId** is used inside of a correlationID block to set the correlation ID.</span></span>  
  
```  
<ic:CorrelationID>  
  <ic:Expression>  
    <wf:Operation Name="GetContextProperty">  
      <wf:Argument>InstanceId</wf:Argument>  
    </wf:Operation>  
  </ic:Expression>  
</ic:CorrelationID>  
```  
  
 <span data-ttu-id="b9336-120">これは `GetContextProperty` の一般的な使用方法です。</span><span class="sxs-lookup"><span data-stu-id="b9336-120">This is a common use of `GetContextProperty`.</span></span>