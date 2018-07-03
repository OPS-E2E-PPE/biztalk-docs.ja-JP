---
title: メッセージの署名に使用する証明書は、ローカル証明書ストアにあることはできません |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2ff3c7a2-954c-4c62-a7b2-06f7a38d61b3
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: feb6a4cc1e5272a4a2c6760ca4585dd0dc10c031
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37001363"
---
# <a name="the-certificate-used-for-signing-a-message-cannot-be-located-in-the-local-certificate-store"></a><span data-ttu-id="c5f16-102">メッセージの署名に使用される証明書を、ローカルの証明書ストアに配置できません</span><span class="sxs-lookup"><span data-stu-id="c5f16-102">The certificate used for signing a message cannot be located in the local certificate store</span></span>
## <a name="details"></a><span data-ttu-id="c5f16-103">詳細</span><span class="sxs-lookup"><span data-stu-id="c5f16-103">Details</span></span>  
  
|                 |                                                                                                                          |
|-----------------|--------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="c5f16-104">製品名</span><span class="sxs-lookup"><span data-stu-id="c5f16-104">Product Name</span></span>   |                    [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                    |
| <span data-ttu-id="c5f16-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="c5f16-105">Product Version</span></span> |                                [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]                                |
|    <span data-ttu-id="c5f16-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="c5f16-106">Event ID</span></span>     |                                                            -                                                             |
|  <span data-ttu-id="c5f16-107">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="c5f16-107">Event Source</span></span>   |                  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="c5f16-108"> EDI</span><span class="sxs-lookup"><span data-stu-id="c5f16-108"> EDI</span></span>                  |
|    <span data-ttu-id="c5f16-109">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="c5f16-109">Component</span></span>    |                                                        <span data-ttu-id="c5f16-110">AS2 エンジン</span><span class="sxs-lookup"><span data-stu-id="c5f16-110">AS2 Engine</span></span>                                                        |
|  <span data-ttu-id="c5f16-111">シンボル名</span><span class="sxs-lookup"><span data-stu-id="c5f16-111">Symbolic Name</span></span>  |                                                 <span data-ttu-id="c5f16-112">CertificateMissingError</span><span class="sxs-lookup"><span data-stu-id="c5f16-112">CertificateMissingError</span></span>                                                  |
|  <span data-ttu-id="c5f16-113">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="c5f16-113">Message Text</span></span>   | <span data-ttu-id="c5f16-114">メッセージの署名に使用される証明書を、ローカルの証明書ストアに配置できません。</span><span class="sxs-lookup"><span data-stu-id="c5f16-114">The certificate used for signing a message cannot be located in the local certificate store.</span></span> <span data-ttu-id="c5f16-115">証明書の拇印: {0}</span><span class="sxs-lookup"><span data-stu-id="c5f16-115">Certificate thumbprint: {0}</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="c5f16-116">説明</span><span class="sxs-lookup"><span data-stu-id="c5f16-116">Explanation</span></span>  
 <span data-ttu-id="c5f16-117">このエラー/警告/情報イベントは、署名証明書として識別された証明書が要求された証明書ストアになかったため、送信パイプラインで送信メッセージを処理できなかったことを示します。</span><span class="sxs-lookup"><span data-stu-id="c5f16-117">This Error/Warning/Information event indicates that the send pipeline could not process the outgoing message because the certificate identified as the signing certificate was not in the required certificate store.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="c5f16-118">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="c5f16-118">User Action</span></span>  
 <span data-ttu-id="c5f16-119">このエラーを解決するには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="c5f16-119">To resolve this error, do the following:</span></span>  
  
1.  <span data-ttu-id="c5f16-120">BizTalk Server 管理コンソールを開いて署名証明書を特定し、[BizTalk グループ] を右クリックして、[証明書] ノードをクリックします。</span><span class="sxs-lookup"><span data-stu-id="c5f16-120">Identify the signing certificate by opening the BizTalk Server Administration Console, right-clicking the BizTalk Group, and then clicking the Certificate node.</span></span>  
  
2.  <span data-ttu-id="c5f16-121">MMC を開き、[ユーザー アカウント] のスナップインを追加して、[証明書] ノード、[個人] ノード、[証明書] ノードの順に開きます。</span><span class="sxs-lookup"><span data-stu-id="c5f16-121">Open MMC, add the snap-in for the My user account, and then open the Certificates, Personal, and Certificates node.</span></span>  
  
3.  <span data-ttu-id="c5f16-122">エラー メッセージ テキストに示された拇印を検索し、現在のユーザーの証明書ストアにその署名証明書の秘密キーが含まれていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="c5f16-122">Make sure that the Current User certificate store contains the private key for that signing certificate by looking for the thumbprint identified in the error message text.</span></span>