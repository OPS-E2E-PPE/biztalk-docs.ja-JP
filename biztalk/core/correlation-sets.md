---
title: 関連付けセット |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
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
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1767755e240171431b01d5997691b800fdbdaa3b
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65354387"
---
# <a name="correlation-sets"></a><span data-ttu-id="5a5d8-102">関連付けセット</span><span class="sxs-lookup"><span data-stu-id="5a5d8-102">Correlation Sets</span></span>
<span data-ttu-id="5a5d8-103">この種のオーケストレーション インスタンスとメッセージの関連付けは、関連付けセットを定義することで実現できます。</span><span class="sxs-lookup"><span data-stu-id="5a5d8-103">You can achieve this sort of correlation of messages with orchestration instances by defining correlation sets.</span></span> <span data-ttu-id="5a5d8-104">関連付けセットは、プロパティのセットを*値を指定して*します。</span><span class="sxs-lookup"><span data-stu-id="5a5d8-104">A correlation set is a set of properties *with specific values*.</span></span> <span data-ttu-id="5a5d8-105">これは、プロパティの一覧だけである関連付けの種類によって異なります。</span><span class="sxs-lookup"><span data-stu-id="5a5d8-105">This is different from a correlation type, which is simply a list of properties.</span></span> <span data-ttu-id="5a5d8-106">受信メッセージがこれらすべてのプロパティにもない場合は、ごとに一致するには、値とは、相関関係の失敗し、オーケストレーション インスタンスによって、メッセージを受信できませんが。</span><span class="sxs-lookup"><span data-stu-id="5a5d8-106">If an incoming message does not have all of these properties, with matching values for each, correlation will fail and the message will not be received by the orchestration instance.</span></span>  
  
 <span data-ttu-id="5a5d8-107">関連付けの種類は、一連のメッセージに関連付けするプロパティを定義します。</span><span class="sxs-lookup"><span data-stu-id="5a5d8-107">Correlation types define a set of properties on which you will be correlating messages.</span></span> <span data-ttu-id="5a5d8-108">BizTalk の基本インストールの一部としてインストールされる GlobalPropertySchemas と共に展開「システム」プロパティを含む一部の BizTalk プロジェクトで以前プロパティ スキーマで定義され、展開のプロパティを指定できます。</span><span class="sxs-lookup"><span data-stu-id="5a5d8-108">These can be any properties which were previously defined in a property schema and deployed with some BizTalk Project including "system" properties deployed with the GlobalPropertySchemas which is installed as part of the base BizTalk install.</span></span> <span data-ttu-id="5a5d8-109">関連付けセットは、特定のオーケストレーションによって処理されるメッセージを含める必要があるこれらのプロパティのプロパティと値のセットを定義します。</span><span class="sxs-lookup"><span data-stu-id="5a5d8-109">A correlation set defines a set of properties and values for these properties that a message must contain to be processed by a particular orchestration.</span></span>  
  
 <span data-ttu-id="5a5d8-110">たとえば、関連付けの種類が、次のプロパティで構成できます。</span><span class="sxs-lookup"><span data-stu-id="5a5d8-110">For example, a correlation type could consist of the following properties:</span></span>  
  
|<span data-ttu-id="5a5d8-111">関連付けの種類のプロパティ</span><span class="sxs-lookup"><span data-stu-id="5a5d8-111">Correlation Type Property</span></span>|<span data-ttu-id="5a5d8-112">使用可能な XML 表現</span><span class="sxs-lookup"><span data-stu-id="5a5d8-112">Possible XML Representation</span></span>|  
|-------------------------------|---------------------------------|  
|<span data-ttu-id="5a5d8-113">社会保障番号</span><span class="sxs-lookup"><span data-stu-id="5a5d8-113">Social Security number</span></span>|<span data-ttu-id="5a5d8-114">\<SSN\>\</SSN\></span><span class="sxs-lookup"><span data-stu-id="5a5d8-114">\<SSN\>\</SSN\></span></span>|  
|<span data-ttu-id="5a5d8-115">生年月日</span><span class="sxs-lookup"><span data-stu-id="5a5d8-115">Date of Birth</span></span>|<span data-ttu-id="5a5d8-116">\<DOB\>\</DOB\></span><span class="sxs-lookup"><span data-stu-id="5a5d8-116">\<DOB\>\</DOB\></span></span>|  
|<span data-ttu-id="5a5d8-117">Gender</span><span class="sxs-lookup"><span data-stu-id="5a5d8-117">Gender</span></span>|<span data-ttu-id="5a5d8-118">\<性別\>\<性別/\></span><span class="sxs-lookup"><span data-stu-id="5a5d8-118">\<Gender\>\</Gender\></span></span>|  
  
 <span data-ttu-id="5a5d8-119">この関連付けの種類から派生した関連付けセットは、次のプロパティの値で構成できます: 中</span><span class="sxs-lookup"><span data-stu-id="5a5d8-119">While a correlation set derived from this correlation type could consist of the following properties and values:</span></span>  
  
|<span data-ttu-id="5a5d8-120">相関関係プロパティと値の設定</span><span class="sxs-lookup"><span data-stu-id="5a5d8-120">Correlation Set Property/Value</span></span>|<span data-ttu-id="5a5d8-121">可能な XML 表現</span><span class="sxs-lookup"><span data-stu-id="5a5d8-121">Possible XML representation</span></span>|  
|-------------------------------------|---------------------------------|  
|<span data-ttu-id="5a5d8-122">社会保障番号 = 222112222</span><span class="sxs-lookup"><span data-stu-id="5a5d8-122">Social Security number = 222112222</span></span>|<span data-ttu-id="5a5d8-123">\<SSN\>222112222\</SSN\></span><span class="sxs-lookup"><span data-stu-id="5a5d8-123">\<SSN\>222112222\</SSN\></span></span>|  
|<span data-ttu-id="5a5d8-124">誕生日 =「1/1/1995」</span><span class="sxs-lookup"><span data-stu-id="5a5d8-124">Date of Birth = “1/1/1995”</span></span>|<span data-ttu-id="5a5d8-125">\<DOB\>「1/1/1995」\</DOB\></span><span class="sxs-lookup"><span data-stu-id="5a5d8-125">\<DOB\>”1/1/1995”\</DOB\></span></span>|  
|<span data-ttu-id="5a5d8-126">Gender = Male</span><span class="sxs-lookup"><span data-stu-id="5a5d8-126">Gender = Male</span></span>|<span data-ttu-id="5a5d8-127">\<性別\>M\<性別/\></span><span class="sxs-lookup"><span data-stu-id="5a5d8-127">\<Gender\>M\</Gender\></span></span>|  
  
> [!NOTE]
>  <span data-ttu-id="5a5d8-128">各関連付けセットには、最大 3 つのパラメーターがサポートしています。</span><span class="sxs-lookup"><span data-stu-id="5a5d8-128">Each correlation set supports a maximum of three parameters.</span></span>  
  
## <a name="initializing-correlation-sets"></a><span data-ttu-id="5a5d8-129">イニシャライズ関連付けセット</span><span class="sxs-lookup"><span data-stu-id="5a5d8-129">Initializing Correlation Sets</span></span>  
  
-   <span data-ttu-id="5a5d8-130">**受信アクションで初期化される関連付けセット**</span><span class="sxs-lookup"><span data-stu-id="5a5d8-130">**Correlation Sets initialized on a Receive action**</span></span>  
  
     <span data-ttu-id="5a5d8-131">アクションでは、存在する必要があるプロパティの正確なセットを定義、対応するで処理するために、公開されたメッセージの受信時に初期化される関連付けセットでは、オーケストレーションのアクションが表示されます。</span><span class="sxs-lookup"><span data-stu-id="5a5d8-131">Correlation sets initialized on a Receive action define the exact set of properties that must exist in a published message in order for it to be processed by the corresponding receive action(s) in an orchestration.</span></span> <span data-ttu-id="5a5d8-132">イニシャライズ関連付けセットは、ドキュメント内の対応する値に基づいて関連付けの種類から関連付けセットを作成します。</span><span class="sxs-lookup"><span data-stu-id="5a5d8-132">An initializing correlation set will create a correlation set from a correlation type based on the corresponding values in a document.</span></span>  
  
-   <span data-ttu-id="5a5d8-133">**送信アクションで初期化される関連付けセット**</span><span class="sxs-lookup"><span data-stu-id="5a5d8-133">**Correlation Sets initialized on a Send action**</span></span>  
  
     <span data-ttu-id="5a5d8-134">送信アクションで初期化される関連付けセットは、ドキュメント内の対応する値に基づいて関連付けの種類から作成し、送信ドキュメントに関連付けのプロパティを昇格させます。</span><span class="sxs-lookup"><span data-stu-id="5a5d8-134">Correlation sets initialized on a Send action are created from a correlation type based upon the corresponding values in a document and promote the correlation properties in the outbound document.</span></span>  
  
## <a name="following-correlation-sets"></a><span data-ttu-id="5a5d8-135">フォロー関連付けセット</span><span class="sxs-lookup"><span data-stu-id="5a5d8-135">Following Correlation Sets</span></span>  
 <span data-ttu-id="5a5d8-136">フォロー関連付けセットは、非アクティブにのみバインドできます受信アクションまたは送信アクションにします。</span><span class="sxs-lookup"><span data-stu-id="5a5d8-136">Following correlation sets can only be bound to a non-activating receive action or to a send action.</span></span> <span data-ttu-id="5a5d8-137">フォロー関連付けセットは、以前に初期化された関連付けセットと連携して指定されます。</span><span class="sxs-lookup"><span data-stu-id="5a5d8-137">Following correlation sets are specified in tandem with previously initialized correlation sets.</span></span>  
  
-   <span data-ttu-id="5a5d8-138">**受信アクションにバインドされたフォロー関連付けセット**</span><span class="sxs-lookup"><span data-stu-id="5a5d8-138">**Following Correlation Sets bound to a Receive action**</span></span>  
  
     <span data-ttu-id="5a5d8-139">フォロー関連付けセットの受信アクションにバインドされたプロパティと、ドキュメントが受信するために含める必要がある値のセットを定義します。</span><span class="sxs-lookup"><span data-stu-id="5a5d8-139">Following correlation sets bound to a receive action define the set of properties and values that the document must contain to be received.</span></span>  <span data-ttu-id="5a5d8-140">受信アクション フォロー関連付けセット、以前に初期化された関連付けセットからのプロパティを含むドキュメントを許可します。</span><span class="sxs-lookup"><span data-stu-id="5a5d8-140">Receive actions with following correlation sets accept documents that contain properties from a previously initialized correlation set.</span></span>  
  
-   <span data-ttu-id="5a5d8-141">**送信アクションにバインドされたフォロー関連付けセット**</span><span class="sxs-lookup"><span data-stu-id="5a5d8-141">**Following Correlation Sets bound to a Send action**</span></span>  
  
     <span data-ttu-id="5a5d8-142">フォロー関連付けセットの送信アクションにバインドされている関連付けセット内のプロパティのセットが送信ドキュメントに昇格させることに影響します。</span><span class="sxs-lookup"><span data-stu-id="5a5d8-142">Following correlation sets bound to a send action dictate that the set of properties in the correlation set are promoted in the outbound document.</span></span>  
  
## <a name="inspecting-correlation-sets"></a><span data-ttu-id="5a5d8-143">関連付けセットの調査</span><span class="sxs-lookup"><span data-stu-id="5a5d8-143">Inspecting Correlation Sets</span></span>  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="5a5d8-144">関連付けセットを調査できるようにをします。</span><span class="sxs-lookup"><span data-stu-id="5a5d8-144">provides the ability to inspect correlation sets.</span></span> <span data-ttu-id="5a5d8-145">関連付けセットには、次のようなコードを使用して、式図形を検査できます。</span><span class="sxs-lookup"><span data-stu-id="5a5d8-145">You can inspect a correlation set in an Expression Shape using code similar to the following:</span></span>  
  
```  
MsgLen = Correlation_1(BTS.MessageLength);  
```  
  
 <span data-ttu-id="5a5d8-146">上記の例は、という名前の変数を作成したことが前提としています**MsgLen**型の**System.Int16**オーケストレーションに相関関係が含まれているとは、名前付きセット**Correlation_1**.</span><span class="sxs-lookup"><span data-stu-id="5a5d8-146">The example above assumes that you have created a variable named **MsgLen** of type **System.Int16** and that your orchestration contains a correlation set named **Correlation_1**.</span></span> <span data-ttu-id="5a5d8-147">関連付けセットを調査する機能は、別のオーケストレーションによってオーケストレーションに渡された関連付けの値を検査する必要がある場合に役立ちます。 可能性があります。</span><span class="sxs-lookup"><span data-stu-id="5a5d8-147">The ability to inspect correlation sets may be useful if you need to inspect the value of a correlation that was passed to an orchestration by another orchestration.</span></span>  
  
## <a name="passing-correlation-sets-as-parameters-to-orchestrations"></a><span data-ttu-id="5a5d8-148">関連付けセットを渡すパラメーターとしてオーケストレーションへ</span><span class="sxs-lookup"><span data-stu-id="5a5d8-148">Passing Correlation Sets as Parameters to Orchestrations</span></span>  
 <span data-ttu-id="5a5d8-149">としての相関関係を渡すことができます*で*他のオーケストレーションにパラメーター。</span><span class="sxs-lookup"><span data-stu-id="5a5d8-149">You can pass correlations as *in* parameters to other orchestrations.</span></span>