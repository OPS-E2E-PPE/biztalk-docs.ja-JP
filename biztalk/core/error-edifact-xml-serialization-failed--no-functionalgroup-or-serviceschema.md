---
title: 無効な構造体、FunctionalGroup または ServiceSchema はないため Edifact インターチェンジの Xml シリアル化に失敗しました |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 530faadd-e301-4743-b4b3-b04ba7578f1d
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f79d64a9ec19e62f13220be056335bf2d249519a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22241442"
---
# <a name="edifact-interchange-xml-serialization-failed-due-to-invalid-structure-no-functionalgroup-or-serviceschema"></a><span data-ttu-id="3d6f0-102">無効な構造により、EDIFACT インターチェンジの XML シリアル化に失敗しました。FunctionalGroup または ServiceSchema はありません</span><span class="sxs-lookup"><span data-stu-id="3d6f0-102">Edifact interchange Xml serialization failed due to invalid structure, no FunctionalGroup or ServiceSchema</span></span>
## <a name="details"></a><span data-ttu-id="3d6f0-103">詳細</span><span class="sxs-lookup"><span data-stu-id="3d6f0-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="3d6f0-104">製品名</span><span class="sxs-lookup"><span data-stu-id="3d6f0-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="3d6f0-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="3d6f0-105">Product Version</span></span>|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|<span data-ttu-id="3d6f0-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="3d6f0-106">Event ID</span></span>|-|  
|<span data-ttu-id="3d6f0-107">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="3d6f0-107">Event Source</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="3d6f0-108"> EDI</span><span class="sxs-lookup"><span data-stu-id="3d6f0-108"> EDI</span></span>|  
|<span data-ttu-id="3d6f0-109">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="3d6f0-109">Component</span></span>|<span data-ttu-id="3d6f0-110">EDI エンジン</span><span class="sxs-lookup"><span data-stu-id="3d6f0-110">EDI Engine</span></span>|  
|<span data-ttu-id="3d6f0-111">シンボル名</span><span class="sxs-lookup"><span data-stu-id="3d6f0-111">Symbolic Name</span></span>|-|  
|<span data-ttu-id="3d6f0-112">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="3d6f0-112">Message Text</span></span>|<span data-ttu-id="3d6f0-113">無効な構造により、EDIFACT インターチェンジの XML シリアル化に失敗しました。</span><span class="sxs-lookup"><span data-stu-id="3d6f0-113">Edifact interchange Xml serialization failed due to invalid structure.</span></span> <span data-ttu-id="3d6f0-114">UNZ の FunctionalGroup または ServiceSchema を検索しましたが、見つかりませんでした。</span><span class="sxs-lookup"><span data-stu-id="3d6f0-114">Looking for FunctionalGroup or ServiceSchema for UNZ, but none found.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="3d6f0-115">説明</span><span class="sxs-lookup"><span data-stu-id="3d6f0-115">Explanation</span></span>  
 <span data-ttu-id="3d6f0-116">このエラー/警告/情報イベントは、TransactionSetGroup または FunctionalGroup タグがインターチェンジ XML ファイルに含まれていなかったため、送信パイプラインが保存された EDIFACT バッチ インターチェンジを処理できなかったことを示します。</span><span class="sxs-lookup"><span data-stu-id="3d6f0-116">This Error/Warning/Information event indicates that the send pipeline could not process an EDIFACT batched interchange that was preserved because the TransactionSetGroup or FunctionalGroup tags were not included in the interchange XML file.</span></span>  
  
 <span data-ttu-id="3d6f0-117">BizTalk が保存されているバッチ インターチェンジを処理する場合、インターチェンジの XML ファイルで、トランザクション セットのグループまたはグループのグループに XML タグが付与されます。</span><span class="sxs-lookup"><span data-stu-id="3d6f0-117">When BizTalk processes a batched interchange that is preserved, a group of transaction sets or a group of groups in the interchange's XML file are given an XML tag.</span></span> <span data-ttu-id="3d6f0-118">グループのグループには、FunctionalGroup タグが付与されます。</span><span class="sxs-lookup"><span data-stu-id="3d6f0-118">A group of groups is given the FunctionalGroup tag.</span></span> <span data-ttu-id="3d6f0-119">ServiceSchema フラグは、保存されたバッチ インターチェンジに対して管理スキーマが使用されることを示します。</span><span class="sxs-lookup"><span data-stu-id="3d6f0-119">The ServiceSchema flag indicates the control schema used for the preserved-batch interchange.</span></span> <span data-ttu-id="3d6f0-120">このエラー状態は、受信パイプラインとパススルー送信パイプラインを使用して、保存されたバッチを設定する場合に発生します。</span><span class="sxs-lookup"><span data-stu-id="3d6f0-120">This error condition occurs if you set up a preserved batch using a receive pipeline and a passthrough transmit send pipeline.</span></span> <span data-ttu-id="3d6f0-121">タグは受信パイプラインによって設定され、送信パイプラインによって除去されます。</span><span class="sxs-lookup"><span data-stu-id="3d6f0-121">The tags are set by the receive pipeline and stripped out by the send pipeline.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="3d6f0-122">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="3d6f0-122">User Action</span></span>  
 <span data-ttu-id="3d6f0-123">このエラーを解決するには、保存されたバッチ用に生成された XML ファイルが、FunctionalGroup タグ (複数のグループ用)、ServiceSchema タグ (保存されたバッチ インターチェンジに使用される管理スキーマ用)、またはその両方を使用した整形式の XML 構造であることを確認します。</span><span class="sxs-lookup"><span data-stu-id="3d6f0-123">To resolve this error, ensure that the XML file generated for the preserved batch has a well-formed XML structure with the FunctionalGroup tag (for multiple groups) and/or the ServiceSchema tag (for the control schema used for the preserved-batch interchange).</span></span>