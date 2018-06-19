---
title: GetActivityProperty |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2321f1ec-d98d-478f-bb1d-a11a98e60fa5
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a55f0d24da85088fb8f13693c8c71d32bee1bef7
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22246586"
---
# <a name="getactivityproperty"></a><span data-ttu-id="54299-102">GetActivityProperty</span><span class="sxs-lookup"><span data-stu-id="54299-102">GetActivityProperty</span></span>
<span data-ttu-id="54299-103">追跡イベントに関連するアクティビティから抽出されたプロパティをスタックにプッシュします。</span><span class="sxs-lookup"><span data-stu-id="54299-103">Pushes the extracted property from the activity related to the tracking event onto the stack.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="54299-104">構文</span><span class="sxs-lookup"><span data-stu-id="54299-104">Syntax</span></span>  
  
```  
  
<wf:Operation Name="GetActivityProperty">  
      <wf:Argument>Arg1</wf:Argument>  
</wf:Operation>  
```  
  
#### <a name="parameters"></a><span data-ttu-id="54299-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="54299-105">Parameters</span></span>  
 <span data-ttu-id="54299-106">プロパティの名前です。</span><span class="sxs-lookup"><span data-stu-id="54299-106">Name of the property.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="54299-107">戻り値</span><span class="sxs-lookup"><span data-stu-id="54299-107">Return Value</span></span>  
 <span data-ttu-id="54299-108">プロパティの値を格納している文字列。</span><span class="sxs-lookup"><span data-stu-id="54299-108">String containing the value of the property.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="54299-109">解説</span><span class="sxs-lookup"><span data-stu-id="54299-109">Remarks</span></span>  
 <span data-ttu-id="54299-110">取得するプロパティ名を修飾するために、ドット付き表記を使用することができます。</span><span class="sxs-lookup"><span data-stu-id="54299-110">You can use dotted-notation for qualifying the property name you want to retrieve.</span></span> <span data-ttu-id="54299-111">これにより、プロパティを通じて公開される他のオブジェクト内のオブジェクトにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="54299-111">This will provide you access to objects inside of other objects exposed through properties.</span></span> <span data-ttu-id="54299-112">たとえば、注文書の Address インスタンスの City プロパティにアクセスするには、"purchaseOrder.Address.City" を使用します。</span><span class="sxs-lookup"><span data-stu-id="54299-112">For example, to access the City property of an Address instance of a purchase order, use "purchaseOrder.Address.City".</span></span>  
  
 <span data-ttu-id="54299-113">プロパティ名は、最初は大文字と小文字が区別され、その後は大文字と小文字が区別されません。</span><span class="sxs-lookup"><span data-stu-id="54299-113">Property names are case-sensitive first, and then case-insensitive.</span></span> <span data-ttu-id="54299-114">これは、WF アプリケーションで、大文字と小文字の区別のみが異なる複数のアクティビティ プロパティを使用する場合に重要です。</span><span class="sxs-lookup"><span data-stu-id="54299-114">This is important when you have two or more activity properties that vary only by case in your WF application.</span></span> <span data-ttu-id="54299-115">たとえば、ワークフロー アプリケーションで "myWorkflow" プロパティと "MyWorkflow" プロパティを定義している場合に "MyWorkflow" を検索すると、大文字と小文字を区別する照合において "MyWorkflow" プロパティが検索されます。</span><span class="sxs-lookup"><span data-stu-id="54299-115">For example, if your workflow application has the properties "myWorkflow" and "MyWorkflow" defined and you were looking for "MyWorkflow", it would match on the second property through a case-sensitive match.</span></span> <span data-ttu-id="54299-116">"MYWORKFLOW" と指定すると、大文字と小文字を区別する照合に失敗してから、大文字と小文字を区別しない照合において "myWorkflow" プロパティが検索されます。</span><span class="sxs-lookup"><span data-stu-id="54299-116">If you specify "MYWORKFLOW", it would match "myWorkflow" through a case-insensitive match after a case-sensitive match attempt fails.</span></span>  
  
 <span data-ttu-id="54299-117">たとえば、大文字と小文字のみが異なる "myProperty" と "MyProperty" の 2 つのアクティビティ プロパティを使用する場合が該当します。</span><span class="sxs-lookup"><span data-stu-id="54299-117">For example, if you have two activity properties that vary only by case: "myProperty" and "MyProperty".</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="54299-118">NULL プロパティ値を使用すると、ワークフロー インスタンスに NullReferenceException がスローされます。</span><span class="sxs-lookup"><span data-stu-id="54299-118">NULL property values will result in a NullReferenceException being thrown back to the workflow instance.</span></span>  
  
## <a name="example"></a><span data-ttu-id="54299-119">例</span><span class="sxs-lookup"><span data-stu-id="54299-119">Example</span></span>  
 <span data-ttu-id="54299-120">次の例では、更新された式でアクティビティ プロパティ "MyProperty" を保持するために、`GetActivityProperty` が使用されています。</span><span class="sxs-lookup"><span data-stu-id="54299-120">In the following sample, an update expression is used to persist the activity property "MyProperty" by using `GetActivityProperty`.</span></span>  
  
```  
<ic:Update DataItemName="TextData" Type="NVARCHAR">  
  <ic:Expression>  
    <wf:Operation Name="GetActivityProperty">  
      <wf:Argument>MyProperty</wf:Argument>  
    </wf:Operation>  
  </ic:Expression>  
</ic:Update>  
```