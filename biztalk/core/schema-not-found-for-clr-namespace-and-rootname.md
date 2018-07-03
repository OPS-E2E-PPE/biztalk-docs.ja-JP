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
ms.openlocfilehash: a830d46a439ad85e5e9e3d54afaca688dac201ca
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36966347"
---
# <a name="schema-not-found-for-clr-namespace-and-rootname"></a><span data-ttu-id="6bd7d-102">CLR Namespace および rootName のスキーマが見つかりません</span><span class="sxs-lookup"><span data-stu-id="6bd7d-102">Schema not found for CLR Namespace and rootName</span></span>
## <a name="details"></a><span data-ttu-id="6bd7d-103">詳細</span><span class="sxs-lookup"><span data-stu-id="6bd7d-103">Details</span></span>  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  <span data-ttu-id="6bd7d-104">製品名</span><span class="sxs-lookup"><span data-stu-id="6bd7d-104">Product Name</span></span>   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| <span data-ttu-id="6bd7d-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="6bd7d-105">Product Version</span></span> |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    <span data-ttu-id="6bd7d-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="6bd7d-106">Event ID</span></span>     |                                           -                                            |
|  <span data-ttu-id="6bd7d-107">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="6bd7d-107">Event Source</span></span>   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="6bd7d-108"> EDI</span><span class="sxs-lookup"><span data-stu-id="6bd7d-108"> EDI</span></span> |
|    <span data-ttu-id="6bd7d-109">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="6bd7d-109">Component</span></span>    |                                       <span data-ttu-id="6bd7d-110">EDI エンジン</span><span class="sxs-lookup"><span data-stu-id="6bd7d-110">EDI Engine</span></span>                                       |
|  <span data-ttu-id="6bd7d-111">シンボル名</span><span class="sxs-lookup"><span data-stu-id="6bd7d-111">Symbolic Name</span></span>  |                               <span data-ttu-id="6bd7d-112">SchemaNotFoundForCLRAndRN</span><span class="sxs-lookup"><span data-stu-id="6bd7d-112">SchemaNotFoundForCLRAndRN</span></span>                                |
|  <span data-ttu-id="6bd7d-113">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="6bd7d-113">Message Text</span></span>   |              <span data-ttu-id="6bd7d-114">スキーマが見つかりません CLR Namespace ={0}および rootName = {1}</span><span class="sxs-lookup"><span data-stu-id="6bd7d-114">Schema not found for CLR Namespace = {0} and rootName = {1}</span></span>               |
  
## <a name="explanation"></a><span data-ttu-id="6bd7d-115">説明</span><span class="sxs-lookup"><span data-stu-id="6bd7d-115">Explanation</span></span>  
 <span data-ttu-id="6bd7d-116">このエラー/警告/情報イベントは、受信パイプラインが、インターチェンジに関連付けられたルート名およびインターチェンジに解決されたパーティに関連付けられた名前空間を使用して、ドキュメント スキーマを見つけられなかったことを示します。</span><span class="sxs-lookup"><span data-stu-id="6bd7d-116">This Error/Warning/Information event indicates that the receive pipeline could not find the document schema using the root name associated with the interchange and the namespace associated with the party that was resolved for the interchange.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="6bd7d-117">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="6bd7d-117">User Action</span></span>  
 <span data-ttu-id="6bd7d-118">このエラーを解決するには、インターチェンジから取得されたルート名および解決されたパーティのプロパティから決定された名前空間が、展開されているスキーマに対応することを確認します。</span><span class="sxs-lookup"><span data-stu-id="6bd7d-118">To resolve this error, ensure that the root name taken from the interchange and the namespace determined from the properties of the resolved party correspond together to a deployed schema.</span></span> <span data-ttu-id="6bd7d-119">BizTalk は、インターチェンジのドキュメントの種類とバージョンからルート名を特定します。</span><span class="sxs-lookup"><span data-stu-id="6bd7d-119">BizTalk determines the root name from the document type and version in the interchange.</span></span> <span data-ttu-id="6bd7d-120">また、インターチェンジ処理のプロパティの [既定のターゲットの名前空間] フィールド (既定のスキーマの場合) または [カスタム トランザクション セットの定義を有効にします] グリッド (カスタム スキーマの場合) からスキーマを特定します。</span><span class="sxs-lookup"><span data-stu-id="6bd7d-120">BizTalk determines the schema from the Default Target Namespace field (for default schemas) or the "Enable custom transaction set definitions" grid (for custom schemas) in the Interchange Processing Properties.</span></span>