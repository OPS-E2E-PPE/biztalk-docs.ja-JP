---
title: メッセージに UNA が含まれていないと、区切り記号のパイプライン プロパティが正しくない形式 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b761d820-e09d-4949-bb41-da9e66054c60
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6310c96f897126a498772f2147a20c84f7e926a0
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22241842"
---
# <a name="message-did-not-contain-una-and-pipeline-property-for-delimiters-was-incorrect-format"></a><span data-ttu-id="51835-102">メッセージに UNA が含まれていなかったため、区切り記号のパイプライン プロパティが正しくない形式になっています</span><span class="sxs-lookup"><span data-stu-id="51835-102">Message did not contain UNA and pipeline property for delimiters was incorrect format</span></span>
## <a name="details"></a><span data-ttu-id="51835-103">詳細</span><span class="sxs-lookup"><span data-stu-id="51835-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="51835-104">製品名</span><span class="sxs-lookup"><span data-stu-id="51835-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="51835-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="51835-105">Product Version</span></span>|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|<span data-ttu-id="51835-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="51835-106">Event ID</span></span>|-|  
|<span data-ttu-id="51835-107">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="51835-107">Event Source</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="51835-108"> EDI</span><span class="sxs-lookup"><span data-stu-id="51835-108"> EDI</span></span>|  
|<span data-ttu-id="51835-109">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="51835-109">Component</span></span>|<span data-ttu-id="51835-110">EDI エンジン</span><span class="sxs-lookup"><span data-stu-id="51835-110">EDI Engine</span></span>|  
|<span data-ttu-id="51835-111">シンボル名</span><span class="sxs-lookup"><span data-stu-id="51835-111">Symbolic Name</span></span>|<span data-ttu-id="51835-112">EfactDelimiterIncorrectFormat</span><span class="sxs-lookup"><span data-stu-id="51835-112">EfactDelimiterIncorrectFormat</span></span>|  
|<span data-ttu-id="51835-113">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="51835-113">Message Text</span></span>|<span data-ttu-id="51835-114">メッセージに UNA が含まれていなかったため、区切り記号のパイプライン プロパティが正しくない形式 '{0}' になっています</span><span class="sxs-lookup"><span data-stu-id="51835-114">Message did not contain UNA and pipeline property for delimiters was incorrect format '{0}'</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="51835-115">説明</span><span class="sxs-lookup"><span data-stu-id="51835-115">Explanation</span></span>  
 <span data-ttu-id="51835-116">このエラー/警告/情報イベントは、インターチェンジの処理に必要な区切り記号を特定できなかったため、受信パイプラインで受信 EDIFACT インターチェンジを処理できなかったことを示します。</span><span class="sxs-lookup"><span data-stu-id="51835-116">This Error/Warning/Information event indicates that the receive pipeline could not process the incoming EDIFACT interchange because it could not determine the separators required to process the interchange.</span></span> <span data-ttu-id="51835-117">このイベントは、インターチェンジに UNA セグメントがなく、EfactDelimiters パイプライン プロパティで正しく区切り記号が定義されていない場合に発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="51835-117">This can occur if the interchange does not have a UNA segment and the EfactDelimiters pipeline property does not adequately define the separators.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="51835-118">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="51835-118">User Action</span></span>  
 <span data-ttu-id="51835-119">このエラーを解決するには、次のいずれかの操作を行います。</span><span class="sxs-lookup"><span data-stu-id="51835-119">To resolve this error, do one of the following:</span></span>  
  
1.  <span data-ttu-id="51835-120">インターチェンジの区切り記号を定義する UNA セグメントがインターチェンジにあることを確認し、インターチェンジを再送信します。</span><span class="sxs-lookup"><span data-stu-id="51835-120">Make sure that the interchange has a UNA segment that defines the separators for the interchange, and then resend the interchange.</span></span>  
  
2.  <span data-ttu-id="51835-121">送信パイプラインの EfactDelimiters パイプライン プロパティを設定します。そのためには、BizTalk Server 管理コンソールを開き、インターチェンジの受信場所を右クリックして、[プロパティ] をクリックします。次に、パイプラインの省略記号をクリックし、区切り記号の値を含む文字列を入力します。</span><span class="sxs-lookup"><span data-stu-id="51835-121">Set the EfactDelimiters pipeline property for the send pipeline by opening the BizTalk Server Administration Console, right-clicking the receive location that will be receiving the interchange, clicking Properties, clicking the ellipsis for the pipeline, and then entering a string containing the values of the separators.</span></span>