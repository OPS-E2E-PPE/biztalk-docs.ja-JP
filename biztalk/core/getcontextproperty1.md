---
title: GetContextProperty1 | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e8867c29-63de-4a13-9ef9-8c6ab8ea3443
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 58e843a8324526e183a577425a015b49c7be3725
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65345125"
---
# <a name="getcontextproperty"></a><span data-ttu-id="7bf14-102">GetContextProperty</span><span class="sxs-lookup"><span data-stu-id="7bf14-102">GetContextProperty</span></span>
<span data-ttu-id="7bf14-103">要求されたコンテキスト プロパティをスタックにプッシュします。</span><span class="sxs-lookup"><span data-stu-id="7bf14-103">Pushes the requested context property onto the stack.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7bf14-104">構文</span><span class="sxs-lookup"><span data-stu-id="7bf14-104">Syntax</span></span>  
  
```  
  
<wcf:Operation Name ="GetContextProperty">  
  <wcf:Argument>EventTime</wcf:Argument>  
</wcf:Operation>  
```  
  
#### <a name="parameters"></a><span data-ttu-id="7bf14-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="7bf14-105">Parameters</span></span>  
 <span data-ttu-id="7bf14-106">次のコンテキスト プロパティ名のいずれかを指定します。</span><span class="sxs-lookup"><span data-stu-id="7bf14-106">One of the following context property names:</span></span>  
  
|<span data-ttu-id="7bf14-107">コンテキスト プロパティ名</span><span class="sxs-lookup"><span data-stu-id="7bf14-107">Context property name</span></span>|<span data-ttu-id="7bf14-108">説明</span><span class="sxs-lookup"><span data-stu-id="7bf14-108">Description</span></span>|  
|---------------------------|-----------------|  
|<span data-ttu-id="7bf14-109">EventTime</span><span class="sxs-lookup"><span data-stu-id="7bf14-109">EventTime</span></span>|<span data-ttu-id="7bf14-110">現在の日付と時刻です。</span><span class="sxs-lookup"><span data-stu-id="7bf14-110">Current date and time.</span></span>|  
|<span data-ttu-id="7bf14-111">SessionId</span><span class="sxs-lookup"><span data-stu-id="7bf14-111">SessionId</span></span>|<span data-ttu-id="7bf14-112">ワークフロー セッション ID です。</span><span class="sxs-lookup"><span data-stu-id="7bf14-112">Workflow session id.</span></span>|  
  
> [!NOTE]
>  <span data-ttu-id="7bf14-113">コンテキスト プロパティ名は大文字と小文字が区別されます。</span><span class="sxs-lookup"><span data-stu-id="7bf14-113">The context property names are case-sensitive.</span></span>  
  
## <a name="pushed-value"></a><span data-ttu-id="7bf14-114">プッシュされた値</span><span class="sxs-lookup"><span data-stu-id="7bf14-114">Pushed Value</span></span>  
 <span data-ttu-id="7bf14-115">要求されたコンテキスト プロパティを表す文字列です。</span><span class="sxs-lookup"><span data-stu-id="7bf14-115">String containing the requested context property.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7bf14-116">コメント</span><span class="sxs-lookup"><span data-stu-id="7bf14-116">Remarks</span></span>  
 <span data-ttu-id="7bf14-117">時刻は UTC 形式でデータベース内部に格納されます。</span><span class="sxs-lookup"><span data-stu-id="7bf14-117">Time is stored in UTC format inside of the database.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7bf14-118">例</span><span class="sxs-lookup"><span data-stu-id="7bf14-118">Example</span></span>  
 <span data-ttu-id="7bf14-119">次に示す更新された式の例では、現在のイベントの時刻を取得することで、承認日を取得します。</span><span class="sxs-lookup"><span data-stu-id="7bf14-119">In the following sample update expression, the approval date is retrieved by retrieving the event time of the current event.</span></span>  
  
```  
<ic:Update DataItemName ="Approval Date" Type ="DATETIME">  
  <ic:Expression>  
    <wcf:Operation Name ="GetContextProperty">  
      <wcf:Argument>EventTime</wcf:Argument>  
    </wcf:Operation>  
  </ic:Expression>  
</ic:Update>  
```  
  
 <span data-ttu-id="7bf14-120">これは `GetContextProperty` の一般的な使用方法です。</span><span class="sxs-lookup"><span data-stu-id="7bf14-120">This is a common use of `GetContextProperty`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7bf14-121">参照</span><span class="sxs-lookup"><span data-stu-id="7bf14-121">See Also</span></span>  
 [<span data-ttu-id="7bf14-122">Windows Communication Foundation での操作</span><span class="sxs-lookup"><span data-stu-id="7bf14-122">Operations in Windows Communication Foundation</span></span>](../core/operations-in-windows-communication-foundation.md)