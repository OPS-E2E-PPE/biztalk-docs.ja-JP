---
title: 'シナリオ: アプリケーション アイテムの更新 |Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- examples, artifacts
- updating, artifacts
- artifacts, examples
- updating, examples
- examples, updating
- artifacts, updating
ms.assetid: 76833df3-2330-48af-84d8-731028b192ff
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0f03e0ac546a638c5eaba9a39b10ba937f3b8d7f
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37018108"
---
# <a name="scenario-updating-application-artifacts"></a><span data-ttu-id="44c7e-102">シナリオ : アプリケーション アイテムの更新</span><span class="sxs-lookup"><span data-stu-id="44c7e-102">Scenario: Updating Application Artifacts</span></span>
<span data-ttu-id="44c7e-103">実稼働環境に展開されたアプリケーションのアイテムを更新する場合、基本的なシナリオとして次の 2 つがあります。</span><span class="sxs-lookup"><span data-stu-id="44c7e-103">There are two basic scenarios for updating the artifacts in an application that has been deployed into a production environment:</span></span>  
  
- <span data-ttu-id="44c7e-104">オーケストレーションが長時間トランザクションを処理する場合、または送信請求 - 応答ポートからの応答を待機している場合に、そのオーケストレーションを新しいバージョンに更新する。</span><span class="sxs-lookup"><span data-stu-id="44c7e-104">Updating an orchestration with a new version when the orchestration handles long-running transactions or is waiting for a response from a solicit-response port.</span></span>  
  
- <span data-ttu-id="44c7e-105">メッセージ処理を完了させることが目的でない場合に行われる、より一般的な更新のケース。たとえば、スキーマまたはマップを新しいバージョンに更新する場合など。</span><span class="sxs-lookup"><span data-stu-id="44c7e-105">The more general update case, when you are not concerned with completing message processing, such as updating a schema or map with a new version.</span></span>  
  
  <span data-ttu-id="44c7e-106">一般的な更新のケースでは、ビジネス要件の変更などに対応するために、アイテムを新しいバージョンに更新することができます。</span><span class="sxs-lookup"><span data-stu-id="44c7e-106">In the general update case, you may be updating an artifact with a new version, for example to address a change in business requirements.</span></span> <span data-ttu-id="44c7e-107">これは比較的簡単なシナリオであり、元のアイテムを更新されたアイテムで上書きできます。</span><span class="sxs-lookup"><span data-stu-id="44c7e-107">This scenario is relatively straightforward, and you can overwrite the original artifact with the updated one.</span></span> <span data-ttu-id="44c7e-108">必要な手順の一覧は、[チェックリスト: BizTalk アプリケーション内のアイテムの更新](../core/checklist-update-the-artifacts-in-a-biztalk-application.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="44c7e-108">For a list of the steps involved, see [Checklist: Update the Artifacts in a BizTalk Application](../core/checklist-update-the-artifacts-in-a-biztalk-application.md).</span></span>  
  
  <span data-ttu-id="44c7e-109">2 番目のシナリオはより複雑です。</span><span class="sxs-lookup"><span data-stu-id="44c7e-109">The second scenario is more complex.</span></span> <span data-ttu-id="44c7e-110">この場合、既存のオーケストレーションがメッセージ処理を完了できるようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="44c7e-110">In this case, you must allow the existing orchestration to finish processing the messages.</span></span> <span data-ttu-id="44c7e-111">同時に、既存のオーケストレーションが新しいメッセージを処理できないようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="44c7e-111">At the same time, you must prevent the existing orchestration from processing any new messages.</span></span> <span data-ttu-id="44c7e-112">代わりに、更新されたバージョンのオーケストレーションによる引き継ぎが必要になります。</span><span class="sxs-lookup"><span data-stu-id="44c7e-112">Instead, you want the updated version of the orchestration to take over.</span></span> <span data-ttu-id="44c7e-113">これを行うには、更新されたオーケストレーションを含むアセンブリを元のバージョンと同じ BizTalk アプリケーションに展開し、両方のオーケストレーションを同時に実行します </span><span class="sxs-lookup"><span data-stu-id="44c7e-113">To accomplish this, you deploy the assembly containing the updated orchestration into the same BizTalk application as the original version, and then run both orchestrations simultaneously.</span></span> <span data-ttu-id="44c7e-114">(新しいアセンブリには、元のオーケストレーションを含むアセンブリとは異なるバージョン番号が必要です。バージョン番号が同一の場合、新しいアセンブリを同じ BizTalk グループに展開することができません)。次に、元のバージョンの参加を解除し、新しいメッセージがこのオーケストレーションに回送されないようにします。その後、更新されたバージョンを開始し、新しいメッセージがすべてこのバージョンに送信されるようにします。</span><span class="sxs-lookup"><span data-stu-id="44c7e-114">(The new assembly must have a different version number than the assembly containing the original orchestration, or you will not be able to deploy it into the same BizTalk group.) You then stop the original orchestration, so that no new messages are routed to it, and start the updated version, so that all new messages are sent to it.</span></span> <span data-ttu-id="44c7e-115">元のバージョンによるメッセージ処理がすべて完了したら、元のバージョンを展開解除することができます。</span><span class="sxs-lookup"><span data-stu-id="44c7e-115">After the original version has finished processing all of its messages, you can then undeploy it.</span></span> <span data-ttu-id="44c7e-116">これらのタスクを実行する方法の詳細については、[オーケストレーションをアップグレードする方法](../core/how-to-upgrade-an-orchestration.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="44c7e-116">For instructions on performing these tasks, see [How to Upgrade an Orchestration](../core/how-to-upgrade-an-orchestration.md).</span></span>  
  
  <span data-ttu-id="44c7e-117">次の図は、標準のオーケストレーション並列展開を示しています。</span><span class="sxs-lookup"><span data-stu-id="44c7e-117">The following diagram shows a typical side-by-side orchestration deployment.</span></span>  
  
  <span data-ttu-id="44c7e-118">![サイド バイ サイド展開シナリオ](../core/media/ebiz-depl-sidebyside-scenario.gif "ebiz_depl_sidebyside_scenario")</span><span class="sxs-lookup"><span data-stu-id="44c7e-118">![Side by Side Deployment Scenario](../core/media/ebiz-depl-sidebyside-scenario.gif "ebiz_depl_sidebyside_scenario")</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="44c7e-119">参照</span><span class="sxs-lookup"><span data-stu-id="44c7e-119">See Also</span></span>  
 <span data-ttu-id="44c7e-120">[アプリケーションの展開と管理のシナリオ](../core/application-deployment-and-management-scenarios.md) </span><span class="sxs-lookup"><span data-stu-id="44c7e-120">[Application Deployment and Management Scenarios](../core/application-deployment-and-management-scenarios.md) </span></span>  
 [<span data-ttu-id="44c7e-121">アプリケーションの更新に関する重要な考慮事項</span><span class="sxs-lookup"><span data-stu-id="44c7e-121">Important Considerations for Updating Applications</span></span>](../core/important-considerations-for-updating-applications.md)