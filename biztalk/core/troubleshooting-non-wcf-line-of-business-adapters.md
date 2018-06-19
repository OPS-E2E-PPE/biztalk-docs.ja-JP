---
title: 非-WCF 基幹業務アダプターのトラブルシューティング |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 4d5f7877-656f-406e-9edb-d6b9a0705b02
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9ba36ed8a8efb62e2eb8e885791c3c28012dcc49
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22279746"
---
# <a name="troubleshooting-non-wcf-line-of-business-adapters"></a><span data-ttu-id="a357e-102">WCF 以外の基幹業務アダプターのトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="a357e-102">Troubleshooting non-WCF Line of Business Adapters</span></span>
## <a name="failed-to-retrieve-error"></a><span data-ttu-id="a357e-103">''取得できませんでした" エラー</span><span class="sxs-lookup"><span data-stu-id="a357e-103">“Failed to retrieve” error</span></span>  
 <span data-ttu-id="a357e-104">WCF 以外の基幹業務 (LOB) アダプターを使用する場合、次のエラーが発生することがあります。</span><span class="sxs-lookup"><span data-stu-id="a357e-104">When using a non-WCF Line of Business (LOB) adapter, the following errors may occur:</span></span>  
  
-   <span data-ttu-id="a357e-105">システムを取得できませんでした</span><span class="sxs-lookup"><span data-stu-id="a357e-105">Failed to retrieve system</span></span>  
  
-   <span data-ttu-id="a357e-106">ブラウジング エージェント: エラーがコンス トラクターにトラップします。</span><span class="sxs-lookup"><span data-stu-id="a357e-106">Browsing agent: Error trapped in constructor.</span></span> <span data-ttu-id="a357e-107">ターゲット マシンは能動的に接続を拒否しました。</span><span class="sxs-lookup"><span data-stu-id="a357e-107">Target machine Actively refused connection.</span></span>  
  
-   <span data-ttu-id="a357e-108">ランタイム エージェント: エラーがコンス トラクターにトラップします。</span><span class="sxs-lookup"><span data-stu-id="a357e-108">Runtime agent: Error trapped in constructor.</span></span> <span data-ttu-id="a357e-109">ターゲット マシンは能動的に接続を拒否しました。</span><span class="sxs-lookup"><span data-stu-id="a357e-109">Target machine Actively refused connection.</span></span>  
  
### <a name="cause"></a><span data-ttu-id="a357e-110">原因</span><span class="sxs-lookup"><span data-stu-id="a357e-110">Cause</span></span>  
 <span data-ttu-id="a357e-111">基幹業務 (LOB) アダプターが .Net リモート処理を使用しています。</span><span class="sxs-lookup"><span data-stu-id="a357e-111">The LOB adapters use .Net Remoting.</span></span> <span data-ttu-id="a357e-112">.Net リモート処理のライセンス認証に予想より時間がかかる場合、アダプターがこれらのエラーを返していることがあります。</span><span class="sxs-lookup"><span data-stu-id="a357e-112">If the .Net Remoting activation takes longer than expected, the adapter may return these errors.</span></span>  
  
### <a name="resolution"></a><span data-ttu-id="a357e-113">解決策</span><span class="sxs-lookup"><span data-stu-id="a357e-113">Resolution</span></span>  
 <span data-ttu-id="a357e-114">作成、 **StartAgentSleep**レジストリ キーとタイムアウト値を大きくします。</span><span class="sxs-lookup"><span data-stu-id="a357e-114">Create the **StartAgentSleep** registry key and increase the timeout value:</span></span>  
  
1.  <span data-ttu-id="a357e-115">レジストリを開きに移動*hkey_local_machine \software\microsoft\biztalkadapters*です。</span><span class="sxs-lookup"><span data-stu-id="a357e-115">Open the registry and go to *HKEY_LOCAL_MACHINE\software\Microsoft\BizTalkAdapters*.</span></span>  
  
2.  <span data-ttu-id="a357e-116">次のプロパティで新しい DWORD 値を作成します。</span><span class="sxs-lookup"><span data-stu-id="a357e-116">Create a new DWORD value with the following properties:</span></span>  
  
     <span data-ttu-id="a357e-117">名前: StartAgentSleep</span><span class="sxs-lookup"><span data-stu-id="a357e-117">Name: StartAgentSleep</span></span>  
  
     <span data-ttu-id="a357e-118">ベース: 10 進数</span><span class="sxs-lookup"><span data-stu-id="a357e-118">Base: Decimal</span></span>  
  
     <span data-ttu-id="a357e-119">値のデータ: 1000</span><span class="sxs-lookup"><span data-stu-id="a357e-119">Value data: 1000</span></span>  
  
 <span data-ttu-id="a357e-120">値のデータはミリ秒 (ms) 単位で指定します。</span><span class="sxs-lookup"><span data-stu-id="a357e-120">Value data is measured in milliseconds (ms).</span></span> <span data-ttu-id="a357e-121">1000ms が 1 秒です。</span><span class="sxs-lookup"><span data-stu-id="a357e-121">1000ms equals 1 second.</span></span>  
  
 <span data-ttu-id="a357e-122">一部のシステムでは 1 秒では足りない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="a357e-122">In some systems, one second may not be enough.</span></span> <span data-ttu-id="a357e-123">値を大きくし、テストして妥当なタイムアウトかどうか判断します。</span><span class="sxs-lookup"><span data-stu-id="a357e-123">Increase the value and test to help determine the appropriate timeout needed.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="a357e-124">追加する、 **StartAgentSleep**レジストリ キーへの影響**すべて**非 WCF LOB アダプター。</span><span class="sxs-lookup"><span data-stu-id="a357e-124">Adding the **StartAgentSleep** registry key impacts **all** the non-WCF LOB adapters.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a357e-125">参照</span><span class="sxs-lookup"><span data-stu-id="a357e-125">See Also</span></span>  
 [<span data-ttu-id="a357e-126">BizTalk Server アダプターのトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="a357e-126">Troubleshooting BizTalk Server Adapters</span></span>](../core/troubleshooting-biztalk-server-adapters.md)