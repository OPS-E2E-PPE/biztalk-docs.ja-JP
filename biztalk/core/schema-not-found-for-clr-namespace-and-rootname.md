---
title: 見つからない CLR Namespace および rootName のスキーマ |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: db283d81-1cb0-460d-ace4-49a91ceb4a02
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1f4a854357a8f1e217273c1a3380a446dcbe7848
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65396924"
---
# <a name="schema-not-found-for-clr-namespace-and-rootname"></a><span data-ttu-id="c882e-102">見つからない CLR Namespace および rootName のスキーマ</span><span class="sxs-lookup"><span data-stu-id="c882e-102">Schema not found for CLR Namespace and rootName</span></span>
## <a name="details"></a><span data-ttu-id="c882e-103">詳細</span><span class="sxs-lookup"><span data-stu-id="c882e-103">Details</span></span>  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  <span data-ttu-id="c882e-104">製品名</span><span class="sxs-lookup"><span data-stu-id="c882e-104">Product Name</span></span>   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| <span data-ttu-id="c882e-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="c882e-105">Product Version</span></span> |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    <span data-ttu-id="c882e-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="c882e-106">Event ID</span></span>     |                                           -                                            |
|  <span data-ttu-id="c882e-107">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="c882e-107">Event Source</span></span>   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="c882e-108">EDI</span><span class="sxs-lookup"><span data-stu-id="c882e-108">EDI</span></span> |
|    <span data-ttu-id="c882e-109">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="c882e-109">Component</span></span>    |                                       <span data-ttu-id="c882e-110">EDI エンジン</span><span class="sxs-lookup"><span data-stu-id="c882e-110">EDI Engine</span></span>                                       |
|  <span data-ttu-id="c882e-111">シンボル名</span><span class="sxs-lookup"><span data-stu-id="c882e-111">Symbolic Name</span></span>  |                               <span data-ttu-id="c882e-112">SchemaNotFoundForCLRAndRN</span><span class="sxs-lookup"><span data-stu-id="c882e-112">SchemaNotFoundForCLRAndRN</span></span>                                |
|  <span data-ttu-id="c882e-113">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="c882e-113">Message Text</span></span>   |              <span data-ttu-id="c882e-114">スキーマが見つかりません CLR Namespace ={0}および rootName = {1}</span><span class="sxs-lookup"><span data-stu-id="c882e-114">Schema not found for CLR Namespace = {0} and rootName = {1}</span></span>               |
  
## <a name="explanation"></a><span data-ttu-id="c882e-115">説明</span><span class="sxs-lookup"><span data-stu-id="c882e-115">Explanation</span></span>  
 <span data-ttu-id="c882e-116">このエラー/警告/情報イベントは、受信パイプラインが、インターチェンジに関連付けられたルート名およびインターチェンジに対して解決されたパーティに関連付けられている名前空間を使用して、ドキュメント スキーマを見つけられなかったことを示します。</span><span class="sxs-lookup"><span data-stu-id="c882e-116">This Error/Warning/Information event indicates that the receive pipeline could not find the document schema using the root name associated with the interchange and the namespace associated with the party that was resolved for the interchange.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="c882e-117">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="c882e-117">User Action</span></span>  
 <span data-ttu-id="c882e-118">このエラーを解決するには、インターチェンジから取得されたルート名と名前空間が解決されるパーティのプロパティから決定が展開されたスキーマにまとめて対応することを確認します。</span><span class="sxs-lookup"><span data-stu-id="c882e-118">To resolve this error, ensure that the root name taken from the interchange and the namespace determined from the properties of the resolved party correspond together to a deployed schema.</span></span> <span data-ttu-id="c882e-119">BizTalk は、ドキュメントの種類と、インターチェンジ内のバージョンからルート名を決定します。</span><span class="sxs-lookup"><span data-stu-id="c882e-119">BizTalk determines the root name from the document type and version in the interchange.</span></span> <span data-ttu-id="c882e-120">BizTalk は、(既定のスキーマ) 用の既定のターゲット Namespace フィールドまたはインターチェンジ処理のプロパティで (カスタム スキーマ用)"を有効にするカスタム トランザクション セットの定義 グリッドからスキーマを決定します。</span><span class="sxs-lookup"><span data-stu-id="c882e-120">BizTalk determines the schema from the Default Target Namespace field (for default schemas) or the "Enable custom transaction set definitions" grid (for custom schemas) in the Interchange Processing Properties.</span></span>