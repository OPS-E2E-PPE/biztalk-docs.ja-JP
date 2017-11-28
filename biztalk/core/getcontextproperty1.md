---
title: "GetContextProperty1 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e8867c29-63de-4a13-9ef9-8c6ab8ea3443
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 65b7ffffe4b21e3317b920ac50cdc27b12d708d5
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="getcontextproperty"></a><span data-ttu-id="4adb2-102">GetContextProperty</span><span class="sxs-lookup"><span data-stu-id="4adb2-102">GetContextProperty</span></span>
<span data-ttu-id="4adb2-103">要求されたコンテキスト プロパティをスタックにプッシュします。</span><span class="sxs-lookup"><span data-stu-id="4adb2-103">Pushes the requested context property onto the stack.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4adb2-104">構文</span><span class="sxs-lookup"><span data-stu-id="4adb2-104">Syntax</span></span>  
  
```  
  
<wcf:Operation Name ="GetContextProperty">  
  <wcf:Argument>EventTime</wcf:Argument>  
</wcf:Operation>  
```  
  
#### <a name="parameters"></a><span data-ttu-id="4adb2-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="4adb2-105">Parameters</span></span>  
 <span data-ttu-id="4adb2-106">次のコンテキスト プロパティ名のいずれかを指定します。</span><span class="sxs-lookup"><span data-stu-id="4adb2-106">One of the following context property names:</span></span>  
  
|<span data-ttu-id="4adb2-107">コンテキスト プロパティ名</span><span class="sxs-lookup"><span data-stu-id="4adb2-107">Context property name</span></span>|<span data-ttu-id="4adb2-108">Description</span><span class="sxs-lookup"><span data-stu-id="4adb2-108">Description</span></span>|  
|---------------------------|-----------------|  
|<span data-ttu-id="4adb2-109">EventTime</span><span class="sxs-lookup"><span data-stu-id="4adb2-109">EventTime</span></span>|<span data-ttu-id="4adb2-110">現在の日付と時刻です。</span><span class="sxs-lookup"><span data-stu-id="4adb2-110">Current date and time.</span></span>|  
|<span data-ttu-id="4adb2-111">SessionId</span><span class="sxs-lookup"><span data-stu-id="4adb2-111">SessionId</span></span>|<span data-ttu-id="4adb2-112">ワークフロー セッション ID です。</span><span class="sxs-lookup"><span data-stu-id="4adb2-112">Workflow session id.</span></span>|  
  
> [!NOTE]
>  <span data-ttu-id="4adb2-113">コンテキスト プロパティ名は大文字と小文字が区別されます。</span><span class="sxs-lookup"><span data-stu-id="4adb2-113">The context property names are case-sensitive.</span></span>  
  
## <a name="pushed-value"></a><span data-ttu-id="4adb2-114">プッシュされた値</span><span class="sxs-lookup"><span data-stu-id="4adb2-114">Pushed Value</span></span>  
 <span data-ttu-id="4adb2-115">要求されたコンテキスト プロパティを表す文字列です。</span><span class="sxs-lookup"><span data-stu-id="4adb2-115">String containing the requested context property.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4adb2-116">解説</span><span class="sxs-lookup"><span data-stu-id="4adb2-116">Remarks</span></span>  
 <span data-ttu-id="4adb2-117">時刻は UTC 形式でデータベース内部に格納されます。</span><span class="sxs-lookup"><span data-stu-id="4adb2-117">Time is stored in UTC format inside of the database.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4adb2-118">例</span><span class="sxs-lookup"><span data-stu-id="4adb2-118">Example</span></span>  
 <span data-ttu-id="4adb2-119">次に示す更新された式の例では、現在のイベントの時刻を取得することで、承認日を取得します。</span><span class="sxs-lookup"><span data-stu-id="4adb2-119">In the following sample update expression, the approval date is retrieved by retrieving the event time of the current event.</span></span>  
  
```  
<ic:Update DataItemName ="Approval Date" Type ="DATETIME">  
  <ic:Expression>  
    <wcf:Operation Name ="GetContextProperty">  
      <wcf:Argument>EventTime</wcf:Argument>  
    </wcf:Operation>  
  </ic:Expression>  
</ic:Update>  
```  
  
 <span data-ttu-id="4adb2-120">これは `GetContextProperty` の一般的な使用方法です。</span><span class="sxs-lookup"><span data-stu-id="4adb2-120">This is a common use of `GetContextProperty`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4adb2-121">参照</span><span class="sxs-lookup"><span data-stu-id="4adb2-121">See Also</span></span>  
 [<span data-ttu-id="4adb2-122">Windows Communication Foundation での操作</span><span class="sxs-lookup"><span data-stu-id="4adb2-122">Operations in Windows Communication Foundation</span></span>](../core/operations-in-windows-communication-foundation.md)