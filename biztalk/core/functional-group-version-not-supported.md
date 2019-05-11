---
title: 機能グループのバージョンがサポートされていません |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 715e6585-a07a-4060-a15b-0c9603fbef19
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: cae2be8619f07de4d0f1178c308b332165b5954e
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65387809"
---
# <a name="functional-group-version-not-supported"></a><span data-ttu-id="4af8e-102">機能グループのバージョンがサポートされていません</span><span class="sxs-lookup"><span data-stu-id="4af8e-102">Functional Group Version Not Supported</span></span>
## <a name="details"></a><span data-ttu-id="4af8e-103">詳細</span><span class="sxs-lookup"><span data-stu-id="4af8e-103">Details</span></span>  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  <span data-ttu-id="4af8e-104">製品名</span><span class="sxs-lookup"><span data-stu-id="4af8e-104">Product Name</span></span>   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| <span data-ttu-id="4af8e-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="4af8e-105">Product Version</span></span> |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    <span data-ttu-id="4af8e-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="4af8e-106">Event ID</span></span>     |                                           -                                            |
|  <span data-ttu-id="4af8e-107">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="4af8e-107">Event Source</span></span>   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="4af8e-108">EDI</span><span class="sxs-lookup"><span data-stu-id="4af8e-108">EDI</span></span> |
|    <span data-ttu-id="4af8e-109">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="4af8e-109">Component</span></span>    |                                       <span data-ttu-id="4af8e-110">EDI エンジン</span><span class="sxs-lookup"><span data-stu-id="4af8e-110">EDI Engine</span></span>                                       |
|  <span data-ttu-id="4af8e-111">シンボル名</span><span class="sxs-lookup"><span data-stu-id="4af8e-111">Symbolic Name</span></span>  |                        <span data-ttu-id="4af8e-112">X12FaGroupVersionNotSupportedDescription</span><span class="sxs-lookup"><span data-stu-id="4af8e-112">X12FaGroupVersionNotSupportedDescription</span></span>                        |
|  <span data-ttu-id="4af8e-113">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="4af8e-113">Message Text</span></span>   |                         <span data-ttu-id="4af8e-114">機能グループのバージョンがサポートされていません</span><span class="sxs-lookup"><span data-stu-id="4af8e-114">Functional Group Version Not Supported</span></span>                         |
  
## <a name="explanation"></a><span data-ttu-id="4af8e-115">説明</span><span class="sxs-lookup"><span data-stu-id="4af8e-115">Explanation</span></span>  
 <span data-ttu-id="4af8e-116">このエラー/警告/情報イベントは、BizTalk Server が、機能グループのセグメント GS08 のバージョン番号をサポートしていないため、受信パイプラインで受信インターチェンジを処理できなかったことを示します。</span><span class="sxs-lookup"><span data-stu-id="4af8e-116">This Error/Warning/Information event indicates that the receive pipeline could not process the incoming interchange because BizTalk Server does not support the version number in segment GS08 of a functional group.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="4af8e-117">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="4af8e-117">User Action</span></span>  
 <span data-ttu-id="4af8e-118">このエラーを解決するには、インターチェンジのすべての機能グループのセグメント GS08 の各インスタンスのバージョン番号が BizTalk Server でサポートされていることを確認してから、インターチェンジを再送信してもらいます。</span><span class="sxs-lookup"><span data-stu-id="4af8e-118">To resolve this error, ensure that the version numbers in each instance of segment GS08 in all functional groups in the interchange are supported by BizTalk Server, and then have the interchange resent.</span></span> <span data-ttu-id="4af8e-119">BizTalk Server がサポートしている標準バージョンは、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 製品ヘルプの「EDI ドキュメント スキーマのサポート」トピックに記載されています。</span><span class="sxs-lookup"><span data-stu-id="4af8e-119">Note that the standard versions that BizTalk Server supports are listed in the "EDI Document Schema Support" topic of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] product help.</span></span>