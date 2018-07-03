---
title: パイプライン コンポーネントからエラーの報告 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- IErrorInfo object
- pipeline components [custom], errors
- SetErrorInfo method
- Exception object
ms.assetid: ad7c519e-829a-4a92-a42f-3e367d5dbaa8
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0a979b894715055b979ecae8c66ecb3fa19ba603
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37018124"
---
# <a name="reporting-errors-from-pipeline-components"></a><span data-ttu-id="90cc2-102">パイプライン コンポーネントからエラーの報告</span><span class="sxs-lookup"><span data-stu-id="90cc2-102">Reporting Errors from Pipeline Components</span></span>
<span data-ttu-id="90cc2-103">パイプライン コンポーネントは、2 種類の方法でエラーを報告します。</span><span class="sxs-lookup"><span data-stu-id="90cc2-103">Pipeline components report errors in two ways:</span></span>  
  
-   <span data-ttu-id="90cc2-104">.NET ベースのコンポーネントの場合は、例外をスローします。</span><span class="sxs-lookup"><span data-stu-id="90cc2-104">For .NET-based components, by throwing an exception.</span></span>  
  
-   <span data-ttu-id="90cc2-105">COM ベースのコンポーネントで設定して、 **ErrorInfo**オブジェクトと HRESULT エラーを返します。</span><span class="sxs-lookup"><span data-stu-id="90cc2-105">For COM-based components, by setting the **ErrorInfo** object and returning a failure HRESULT.</span></span>  
  
## <a name="reporting-errors-from-net-pipeline-components"></a><span data-ttu-id="90cc2-106">.NET パイプライン コンポーネントからのエラーの報告</span><span class="sxs-lookup"><span data-stu-id="90cc2-106">Reporting errors from .NET pipeline components</span></span>  
 <span data-ttu-id="90cc2-107">.NET ベースのパイプライン コンポーネントは、エラーを報告するために、例外をスローしてエラーの説明を通知する必要があります。</span><span class="sxs-lookup"><span data-stu-id="90cc2-107">To report an error, a .NET-based pipeline component needs to throw an exception where it reports the error description.</span></span> <span data-ttu-id="90cc2-108">エラーをスローするコンポーネントの名前を報告するには、設定、**ソース**のプロパティ、**例外**オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="90cc2-108">To report the name of the component that throws an error, set the **Source** property of the **Exception** object.</span></span>  
  
 <span data-ttu-id="90cc2-109">メッセージング エンジンを使用して、**メッセージ**と**ソース**のプロパティ、**例外**エラーを報告するオブジェクト。</span><span class="sxs-lookup"><span data-stu-id="90cc2-109">The Messaging Engine uses the **Message** and **Source** properties of the **Exception** object to report an error.</span></span> <span data-ttu-id="90cc2-110">次のメッセージがイベント ログに書き込まれます。</span><span class="sxs-lookup"><span data-stu-id="90cc2-110">The following message is written to the event log:</span></span>  
  
 <span data-ttu-id="90cc2-111">"が失敗した実行、[受信&#124;送信] パイプライン:\<パイプライン名\>ソース:\<ソース\>[受信場所&#124;送信ポート:]\<場所&#124;ポート名\>理由:\<メッセージ\>"。</span><span class="sxs-lookup"><span data-stu-id="90cc2-111">"There was a failure executing the [receive&#124;send] pipeline: \<pipeline name\> Source: \<Source\> [Receive Location&#124;Send Port:] \<location&#124;port name\> Reason: \<Message\>."</span></span>  
  
## <a name="reporting-errors-from-com-pipeline-components"></a><span data-ttu-id="90cc2-112">COM パイプライン コンポーネントからのエラーの報告</span><span class="sxs-lookup"><span data-stu-id="90cc2-112">Reporting errors from COM pipeline components</span></span>  
 <span data-ttu-id="90cc2-113">COM ベースのパイプライン コンポーネントは、エラーを報告するために以下のアクションを実行します。</span><span class="sxs-lookup"><span data-stu-id="90cc2-113">To report an error, COM-based pipeline components perform the following actions:</span></span>  
  
1. <span data-ttu-id="90cc2-114">パイプライン コンポーネントのセット、 **IErrorInfo**オブジェクトを呼び出すことによって、 **SetErrorInfo**メソッド。</span><span class="sxs-lookup"><span data-stu-id="90cc2-114">The pipeline component sets the **IErrorInfo** object by calling the **SetErrorInfo** method.</span></span>  
  
2. <span data-ttu-id="90cc2-115">パイプライン コンポーネントは、HRESULT エラーをメッセージング エンジンに返します。</span><span class="sxs-lookup"><span data-stu-id="90cc2-115">The pipeline component returns a failed HRESULT to the Messaging Engine.</span></span>  
  
   <span data-ttu-id="90cc2-116">メッセージング エンジンを使用して、 **GetSource**と**GetDescription**のプロパティ、 **IErrorInfo**エラーを報告するオブジェクト。</span><span class="sxs-lookup"><span data-stu-id="90cc2-116">The Messaging Engine uses the **GetSource** and **GetDescription** properties of the **IErrorInfo** object to report an error.</span></span> <span data-ttu-id="90cc2-117">送信元が設定されていない場合は、コンポーネントの名前を使用します。</span><span class="sxs-lookup"><span data-stu-id="90cc2-117">If the source is not set, the name of the component is used.</span></span> <span data-ttu-id="90cc2-118">説明のセットまたは全体がない場合**ErrorInfo**オブジェクトが設定されていない、返された HRESULT は、説明ではなく報告されます。</span><span class="sxs-lookup"><span data-stu-id="90cc2-118">If the description is not set or the whole **ErrorInfo** object is not set, the returned HRESULT is reported instead of the description.</span></span> <span data-ttu-id="90cc2-119">次のメッセージがイベント ログに書き込まれます。</span><span class="sxs-lookup"><span data-stu-id="90cc2-119">The following message is written to the event log:</span></span>  
  
   <span data-ttu-id="90cc2-120">"が失敗した実行、[受信&#124;送信] パイプライン:\<パイプライン名\>ソース: \<GetSource\> [受信場所&#124;送信ポート:]\<場所&#124;ポート名\>理由: \<GetDescription または HRESULT\>"。</span><span class="sxs-lookup"><span data-stu-id="90cc2-120">"There was a failure executing the [receive&#124;send] pipeline: \<pipeline name\> Source: \<GetSource\> [Receive Location&#124;Send Port:] \<location&#124;port name\> Reason: \<GetDescription or HRESULT\>."</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="90cc2-121">参照</span><span class="sxs-lookup"><span data-stu-id="90cc2-121">See Also</span></span>  
 [<span data-ttu-id="90cc2-122">カスタム パイプライン コンポーネントの開発</span><span class="sxs-lookup"><span data-stu-id="90cc2-122">Developing Custom Pipeline Components</span></span>](../core/developing-custom-pipeline-components.md)