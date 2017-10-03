---
title: "関連付けセット |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- correlation sets, inspecting
- correlation sets, about correlation sets
- correlation sets, passing as parameters
- messages, correlation sets
- correlation sets
- correlation sets, following correlation sets
- correlation sets, initializing
ms.assetid: 528dcd6c-d364-4bb8-8deb-cd4a0791867f
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 28d11e5e174808ca7718d5fef98b3ad079cffc18
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="correlation-sets"></a><span data-ttu-id="6364a-102">関連付けセット</span><span class="sxs-lookup"><span data-stu-id="6364a-102">Correlation Sets</span></span>
<span data-ttu-id="6364a-103">関連付けセットを定義することによって、オーケストレーション インスタンスを使用して、このようなメッセージの関連付けを行うことができます。</span><span class="sxs-lookup"><span data-stu-id="6364a-103">You can achieve this sort of correlation of messages with orchestration instances by defining correlation sets.</span></span> <span data-ttu-id="6364a-104">関連付けセットは、一連のプロパティ*値を指定して*です。</span><span class="sxs-lookup"><span data-stu-id="6364a-104">A correlation set is a set of properties *with specific values*.</span></span> <span data-ttu-id="6364a-105">これは、単なるプロパティの一覧である関連付けの種類とは異なります。</span><span class="sxs-lookup"><span data-stu-id="6364a-105">This is different from a correlation type, which is simply a list of properties.</span></span> <span data-ttu-id="6364a-106">受信メッセージがそれぞれに一致する値を持つこれらのプロパティの一部を持っていない場合は、関連付けは失敗し、オーケストレーション インスタンスはメッセージを受信しません。</span><span class="sxs-lookup"><span data-stu-id="6364a-106">If an incoming message does not have all of these properties, with matching values for each, correlation will fail and the message will not be received by the orchestration instance.</span></span>  
  
 <span data-ttu-id="6364a-107">関連付けセットは、メッセージを関連付けるプロパティのセットを定義します。</span><span class="sxs-lookup"><span data-stu-id="6364a-107">Correlation types define a set of properties on which you will be correlating messages.</span></span> <span data-ttu-id="6364a-108">これらは、プロパティ スキーマで前に定義された任意のプロパティにすることができ、BizTalk の基本インストールの一部としてインストールされる GlobalPropertySchemas と共に展開された "システム" のプロパティを含む一部の BizTalk プロジェクトを使用して展開できます。</span><span class="sxs-lookup"><span data-stu-id="6364a-108">These can be any properties which were previously defined in a property schema and deployed with some BizTalk Project including "system" properties deployed with the GlobalPropertySchemas which is installed as part of the base BizTalk install.</span></span> <span data-ttu-id="6364a-109">関連付けセットでは、メッセージが特定のオーケストレーションでの処理対象となるために、メッセージに含まれている必要がある一連のプロパティとその値を定義します。</span><span class="sxs-lookup"><span data-stu-id="6364a-109">A correlation set defines a set of properties and values for these properties that a message must contain to be processed by a particular orchestration.</span></span>  
  
 <span data-ttu-id="6364a-110">たとえば、関連付けの種類は、次のプロパティで構成される可能性が考えられます。</span><span class="sxs-lookup"><span data-stu-id="6364a-110">For example, a correlation type could consist of the following properties:</span></span>  
  
|<span data-ttu-id="6364a-111">関連付けの種類のプロパティ</span><span class="sxs-lookup"><span data-stu-id="6364a-111">Correlation Type Property</span></span>|<span data-ttu-id="6364a-112">使用可能な XML 表記</span><span class="sxs-lookup"><span data-stu-id="6364a-112">Possible XML Representation</span></span>|  
|-------------------------------|---------------------------------|  
|<span data-ttu-id="6364a-113">社会保障番号</span><span class="sxs-lookup"><span data-stu-id="6364a-113">Social Security number</span></span>|<span data-ttu-id="6364a-114">\<SSN >\</SSN ></span><span class="sxs-lookup"><span data-stu-id="6364a-114">\<SSN>\</SSN></span></span>|  
|<span data-ttu-id="6364a-115">誕生日</span><span class="sxs-lookup"><span data-stu-id="6364a-115">Date of Birth</span></span>|<span data-ttu-id="6364a-116">\<DOB >\</DOB ></span><span class="sxs-lookup"><span data-stu-id="6364a-116">\<DOB>\</DOB></span></span>|  
|<span data-ttu-id="6364a-117">Gender</span><span class="sxs-lookup"><span data-stu-id="6364a-117">Gender</span></span>|<span data-ttu-id="6364a-118">\<性別 >\<性別/></span><span class="sxs-lookup"><span data-stu-id="6364a-118">\<Gender>\</Gender></span></span>|  
  
 <span data-ttu-id="6364a-119">この関連付けの種類から派生した関連付けセットは、次のプロパティと値で構成される可能性が考えられます。</span><span class="sxs-lookup"><span data-stu-id="6364a-119">While a correlation set derived from this correlation type could consist of the following properties and values:</span></span>  
  
|<span data-ttu-id="6364a-120">関連付けセットのプロパティおよび値</span><span class="sxs-lookup"><span data-stu-id="6364a-120">Correlation Set Property/Value</span></span>|<span data-ttu-id="6364a-121">可能な XML 表現</span><span class="sxs-lookup"><span data-stu-id="6364a-121">Possible XML representation</span></span>|  
|-------------------------------------|---------------------------------|  
|<span data-ttu-id="6364a-122">社会保障番号 = 222112222</span><span class="sxs-lookup"><span data-stu-id="6364a-122">Social Security number = 222112222</span></span>|<span data-ttu-id="6364a-123">\<SSN > 222112222\</SSN ></span><span class="sxs-lookup"><span data-stu-id="6364a-123">\<SSN>222112222\</SSN></span></span>|  
|<span data-ttu-id="6364a-124">誕生日 = “1/1/1995”</span><span class="sxs-lookup"><span data-stu-id="6364a-124">Date of Birth = “1/1/1995”</span></span>|<span data-ttu-id="6364a-125">\<DOB >「1/1/1995」\</DOB ></span><span class="sxs-lookup"><span data-stu-id="6364a-125">\<DOB>”1/1/1995”\</DOB></span></span>|  
|<span data-ttu-id="6364a-126">性別 = 男性</span><span class="sxs-lookup"><span data-stu-id="6364a-126">Gender = Male</span></span>|<span data-ttu-id="6364a-127">\<性別 > M\<性別/></span><span class="sxs-lookup"><span data-stu-id="6364a-127">\<Gender>M\</Gender></span></span>|  
  
> [!NOTE]
>  <span data-ttu-id="6364a-128">各関連付けセットは最大 3 つのパラメーターをサポートします。</span><span class="sxs-lookup"><span data-stu-id="6364a-128">Each correlation set supports a maximum of three parameters.</span></span>  
  
## <a name="initializing-correlation-sets"></a><span data-ttu-id="6364a-129">イニシャライズ関連付けセット</span><span class="sxs-lookup"><span data-stu-id="6364a-129">Initializing Correlation Sets</span></span>  
  
-   <span data-ttu-id="6364a-130">**受信アクションで初期化される関連付けセット**</span><span class="sxs-lookup"><span data-stu-id="6364a-130">**Correlation Sets initialized on a Receive action**</span></span>  
  
     <span data-ttu-id="6364a-131">受信アクションで初期化される関連付けセットは、オーケストレーションの対応する受信アクションによって処理されるように、公開されたメッセージに存在する必要がある正確なプロパティのセットだけを定義します。</span><span class="sxs-lookup"><span data-stu-id="6364a-131">Correlation sets initialized on a Receive action define the exact set of properties that must exist in a published message in order for it to be processed by the corresponding receive action(s) in an orchestration.</span></span> <span data-ttu-id="6364a-132">関連付けセットの初期化によって、ドキュメント内の対応する値に基づいて関連付けの種類から関連付けセットが作成されます。</span><span class="sxs-lookup"><span data-stu-id="6364a-132">An initializing correlation set will create a correlation set from a correlation type based on the corresponding values in a document.</span></span>  
  
-   <span data-ttu-id="6364a-133">**送信アクションで初期化される関連付けセット**</span><span class="sxs-lookup"><span data-stu-id="6364a-133">**Correlation Sets initialized on a Send action**</span></span>  
  
     <span data-ttu-id="6364a-134">送信アクションで初期化される関連付けセットは、ドキュメント内の対応する値に基づいて関連付けの種類から作成され、送信ドキュメント内の関連付けのプロパティを昇格させます。</span><span class="sxs-lookup"><span data-stu-id="6364a-134">Correlation sets initialized on a Send action are created from a correlation type based upon the corresponding values in a document and promote the correlation properties in the outbound document.</span></span>  
  
## <a name="following-correlation-sets"></a><span data-ttu-id="6364a-135">フォロー関連付けセット</span><span class="sxs-lookup"><span data-stu-id="6364a-135">Following Correlation Sets</span></span>  
 <span data-ttu-id="6364a-136">フォロー関連付けセットは、非アクティブ化受信アクションまたは送信アクションだけに対してバインドできます。</span><span class="sxs-lookup"><span data-stu-id="6364a-136">Following correlation sets can only be bound to a non-activating receive action or to a send action.</span></span> <span data-ttu-id="6364a-137">フォロー関連付けセットは、前に初期化された関連付けセットと共に指定されます。</span><span class="sxs-lookup"><span data-stu-id="6364a-137">Following correlation sets are specified in tandem with previously initialized correlation sets.</span></span>  
  
-   <span data-ttu-id="6364a-138">**受信アクションにバインドされたフォロー関連付けセット**</span><span class="sxs-lookup"><span data-stu-id="6364a-138">**Following Correlation Sets bound to a Receive action**</span></span>  
  
     <span data-ttu-id="6364a-139">受信アクションにバインドされているフォロー関連付けセットは、ドキュメントが受信されるためにそのドキュメントに含める必要があるプロパティと値のセットを定義します。</span><span class="sxs-lookup"><span data-stu-id="6364a-139">Following correlation sets bound to a receive action define the set of properties and values that the document must contain to be received.</span></span>  <span data-ttu-id="6364a-140">フォロー関連付けセットを持つ受信アクションは、前に初期化された関連付けセットからのプロパティを含むドキュメントを受け入れます。</span><span class="sxs-lookup"><span data-stu-id="6364a-140">Receive actions with following correlation sets accept documents that contain properties from a previously initialized correlation set.</span></span>  
  
-   <span data-ttu-id="6364a-141">**送信アクションにバインドされたフォロー関連付けセット**</span><span class="sxs-lookup"><span data-stu-id="6364a-141">**Following Correlation Sets bound to a Send action**</span></span>  
  
     <span data-ttu-id="6364a-142">送信アクションにバインドされているフォロー関連付けセットは、関連付けセットのプロパティのセットが送信ドキュメントで昇格されることを指示します。</span><span class="sxs-lookup"><span data-stu-id="6364a-142">Following correlation sets bound to a send action dictate that the set of properties in the correlation set are promoted in the outbound document.</span></span>  
  
## <a name="inspecting-correlation-sets"></a><span data-ttu-id="6364a-143">関連付けセットの調査</span><span class="sxs-lookup"><span data-stu-id="6364a-143">Inspecting Correlation Sets</span></span>  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="6364a-144"> では、関連付けセットを調査する機能が提供されます。</span><span class="sxs-lookup"><span data-stu-id="6364a-144"> provides the ability to inspect correlation sets.</span></span> <span data-ttu-id="6364a-145">次のようなコードを使用して、式図形の関連付けセットを調査できます。</span><span class="sxs-lookup"><span data-stu-id="6364a-145">You can inspect a correlation set in an Expression Shape using code similar to the following:</span></span>  
  
```  
MsgLen = Correlation_1(BTS.MessageLength);  
```  
  
 <span data-ttu-id="6364a-146">上記の例は、という名前の変数を作成している前提としています**MsgLen**型の**System.Int16** 、オーケストレーションに相関関係が含まれているとは、名前付きセット**Correlation_1**。.</span><span class="sxs-lookup"><span data-stu-id="6364a-146">The example above assumes that you have created a variable named **MsgLen** of type **System.Int16** and that your orchestration contains a correlation set named **Correlation_1**.</span></span> <span data-ttu-id="6364a-147">関連付けセットを調査する機能は、別のオーケストレーションによってオーケストレーションに渡された関連付けの値を調査する必要がある場合に、役立つことがあります。</span><span class="sxs-lookup"><span data-stu-id="6364a-147">The ability to inspect correlation sets may be useful if you need to inspect the value of a correlation that was passed to an orchestration by another orchestration.</span></span>  
  
## <a name="passing-correlation-sets-as-parameters-to-orchestrations"></a><span data-ttu-id="6364a-148">オーケストレーションにパラメーターとして関連付けセットを渡す</span><span class="sxs-lookup"><span data-stu-id="6364a-148">Passing Correlation Sets as Parameters to Orchestrations</span></span>  
 <span data-ttu-id="6364a-149">相関関係を渡すことができます*で*他のオーケストレーションへのパラメーターです。</span><span class="sxs-lookup"><span data-stu-id="6364a-149">You can pass correlations as *in* parameters to other orchestrations.</span></span>