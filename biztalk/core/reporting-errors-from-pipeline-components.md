---
title: パイプライン コンポーネントからエラーを報告 |Microsoft ドキュメント
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
ms.openlocfilehash: 1c111a0c10f4316e7b29e873adf53a8e6b9a9acd
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
ms.locfileid: "25976040"
---
# <a name="reporting-errors-from-pipeline-components"></a><span data-ttu-id="a211b-102">パイプライン コンポーネントからエラーの報告</span><span class="sxs-lookup"><span data-stu-id="a211b-102">Reporting Errors from Pipeline Components</span></span>
<span data-ttu-id="a211b-103">パイプライン コンポーネントは、2 種類の方法でエラーを報告します。</span><span class="sxs-lookup"><span data-stu-id="a211b-103">Pipeline components report errors in two ways:</span></span>  
  
-   <span data-ttu-id="a211b-104">.NET ベースのコンポーネントの場合は、例外をスローします。</span><span class="sxs-lookup"><span data-stu-id="a211b-104">For .NET-based components, by throwing an exception.</span></span>  
  
-   <span data-ttu-id="a211b-105">COM ベースのコンポーネントで設定して、 **ErrorInfo**オブジェクトと HRESULT エラーを返します。</span><span class="sxs-lookup"><span data-stu-id="a211b-105">For COM-based components, by setting the **ErrorInfo** object and returning a failure HRESULT.</span></span>  
  
## <a name="reporting-errors-from-net-pipeline-components"></a><span data-ttu-id="a211b-106">.NET パイプライン コンポーネントからのエラーの報告</span><span class="sxs-lookup"><span data-stu-id="a211b-106">Reporting errors from .NET pipeline components</span></span>  
 <span data-ttu-id="a211b-107">.NET ベースのパイプライン コンポーネントは、エラーを報告するために、例外をスローしてエラーの説明を通知する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a211b-107">To report an error, a .NET-based pipeline component needs to throw an exception where it reports the error description.</span></span> <span data-ttu-id="a211b-108">エラーをスローしたコンポーネントの名前を報告するには、設定、**ソース**のプロパティ、**例外**オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="a211b-108">To report the name of the component that throws an error, set the **Source** property of the **Exception** object.</span></span>  
  
 <span data-ttu-id="a211b-109">メッセージング エンジンを使用して、**メッセージ**と**ソース**のプロパティ、**例外**エラーを報告するオブジェクト。</span><span class="sxs-lookup"><span data-stu-id="a211b-109">The Messaging Engine uses the **Message** and **Source** properties of the **Exception** object to report an error.</span></span> <span data-ttu-id="a211b-110">次のメッセージがイベント ログに書き込まれます。</span><span class="sxs-lookup"><span data-stu-id="a211b-110">The following message is written to the event log:</span></span>  
  
 <span data-ttu-id="a211b-111">"エラーが発生しましたを実行する、[受信 (& a) #124; 送信] パイプライン:\<パイプライン名\>ソース:\<ソース\>[受信場所 (&) #124 です。送信ポート:]\<場所 (&) #124 ですポート名\>理由:\<メッセージ\>。"。</span><span class="sxs-lookup"><span data-stu-id="a211b-111">"There was a failure executing the [receive&#124;send] pipeline: \<pipeline name\> Source: \<Source\> [Receive Location&#124;Send Port:] \<location&#124;port name\> Reason: \<Message\>."</span></span>  
  
## <a name="reporting-errors-from-com-pipeline-components"></a><span data-ttu-id="a211b-112">COM パイプライン コンポーネントからのエラーの報告</span><span class="sxs-lookup"><span data-stu-id="a211b-112">Reporting errors from COM pipeline components</span></span>  
 <span data-ttu-id="a211b-113">COM ベースのパイプライン コンポーネントは、エラーを報告するために以下のアクションを実行します。</span><span class="sxs-lookup"><span data-stu-id="a211b-113">To report an error, COM-based pipeline components perform the following actions:</span></span>  
  
1.  <span data-ttu-id="a211b-114">パイプライン コンポーネント セット、 **IErrorInfo**オブジェクトを呼び出して、 **SetErrorInfo**メソッドです。</span><span class="sxs-lookup"><span data-stu-id="a211b-114">The pipeline component sets the **IErrorInfo** object by calling the **SetErrorInfo** method.</span></span>  
  
2.  <span data-ttu-id="a211b-115">パイプライン コンポーネントは、HRESULT エラーをメッセージング エンジンに返します。</span><span class="sxs-lookup"><span data-stu-id="a211b-115">The pipeline component returns a failed HRESULT to the Messaging Engine.</span></span>  
  
 <span data-ttu-id="a211b-116">メッセージング エンジンを使用して、 **GetSource**と**GetDescription**のプロパティ、 **IErrorInfo**エラーを報告するオブジェクト。</span><span class="sxs-lookup"><span data-stu-id="a211b-116">The Messaging Engine uses the **GetSource** and **GetDescription** properties of the **IErrorInfo** object to report an error.</span></span> <span data-ttu-id="a211b-117">送信元が設定されていない場合は、コンポーネントの名前を使用します。</span><span class="sxs-lookup"><span data-stu-id="a211b-117">If the source is not set, the name of the component is used.</span></span> <span data-ttu-id="a211b-118">説明設定されていないか、全体場合**ErrorInfo**オブジェクトが設定されていない、返された HRESULT を報告、説明の代わりにします。</span><span class="sxs-lookup"><span data-stu-id="a211b-118">If the description is not set or the whole **ErrorInfo** object is not set, the returned HRESULT is reported instead of the description.</span></span> <span data-ttu-id="a211b-119">次のメッセージがイベント ログに書き込まれます。</span><span class="sxs-lookup"><span data-stu-id="a211b-119">The following message is written to the event log:</span></span>  
  
 <span data-ttu-id="a211b-120">"エラーが発生しましたを実行する、[受信 (& a) #124; 送信] パイプライン:\<パイプライン名\>ソース: \<GetSource\> [受信場所 (&) #124 です。送信ポート:]\<場所 (&) #124 ですポート名\>理由: \<GetDescription または HRESULT\>。"。</span><span class="sxs-lookup"><span data-stu-id="a211b-120">"There was a failure executing the [receive&#124;send] pipeline: \<pipeline name\> Source: \<GetSource\> [Receive Location&#124;Send Port:] \<location&#124;port name\> Reason: \<GetDescription or HRESULT\>."</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a211b-121">参照</span><span class="sxs-lookup"><span data-stu-id="a211b-121">See Also</span></span>  
 [<span data-ttu-id="a211b-122">カスタム パイプライン コンポーネントの開発</span><span class="sxs-lookup"><span data-stu-id="a211b-122">Developing Custom Pipeline Components</span></span>](../core/developing-custom-pipeline-components.md)