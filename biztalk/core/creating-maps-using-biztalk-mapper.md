---
title: BizTalk マッパーを使用してマップを作成 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- creating, maps
- maps, creating
- orchestrations, maps
- translations [maps]
- maps, about maps
- transformations [maps]
- maps
ms.assetid: 265e61d8-8cff-44c9-a717-8e895cb4b9bf
caps.latest.revision: 20
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b295fbe516c6a30f7244dbfe0cbec83480ec0bba
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65389921"
---
# <a name="creating-maps-using-biztalk-mapper"></a><span data-ttu-id="8a29d-102">BizTalk マッパーでのマップの作成</span><span class="sxs-lookup"><span data-stu-id="8a29d-102">Creating Maps Using BizTalk Mapper</span></span>
<span data-ttu-id="8a29d-103">BizTalk マッパーは、Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] 環境内で動作するツールです。</span><span class="sxs-lookup"><span data-stu-id="8a29d-103">BizTalk Mapper is a tool that runs within the Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] environment.</span></span> <span data-ttu-id="8a29d-104">BizTalk マッパーを使用すると、XML メッセージの変換に必要なマップを作成および編集できます。</span><span class="sxs-lookup"><span data-stu-id="8a29d-104">BizTalk Mapper can be used to create and edit maps, which are used for translating or transforming xml messages.</span></span> <span data-ttu-id="8a29d-105">マップは、オーケストレーション (次の図を参照) に使用されるほか、受信ポートで受け取ったメッセージを処理し、変換を適用してから、送信ポートを介して送信するという目的にも使用されます。</span><span class="sxs-lookup"><span data-stu-id="8a29d-105">Maps are used in orchestrations, as the following figure suggest, and can also be used for processing messages received at a receive port, and then transforming the message to be sent via send port(s).</span></span>  
  
 <span data-ttu-id="8a29d-106">![マップとビジネス プロセス ダイアグラム。](../core/media/ebiz-dev-busprcsg.gif "ebiz_dev_busprcsg")</span><span class="sxs-lookup"><span data-stu-id="8a29d-106">![Business processing diagram with maps.](../core/media/ebiz-dev-busprcsg.gif "ebiz_dev_busprcsg")</span></span>  
<span data-ttu-id="8a29d-107">ビジネス プロセスのマップ</span><span class="sxs-lookup"><span data-stu-id="8a29d-107">Maps in Business Processing</span></span>  
  
 <span data-ttu-id="8a29d-108">マップを使用して、メッセージを変換 (トランスレートまたはトランスフォーム) できます。</span><span class="sxs-lookup"><span data-stu-id="8a29d-108">Maps enable you to translate and to transform messages.</span></span> <span data-ttu-id="8a29d-109">トランスレートは、フラット ファイルから XML ファイルへの変換など、ある形式から別の形式にメッセージを変換する処理です。</span><span class="sxs-lookup"><span data-stu-id="8a29d-109">Translation is the process of converting a message from one format to another format, such as converting a flat file into an XML file.</span></span> <span data-ttu-id="8a29d-110">トランスフォームは、あるメッセージから情報を取得し、別のメッセージにその情報を挿入する処理です。</span><span class="sxs-lookup"><span data-stu-id="8a29d-110">Transformation is the process of taking information from one message and inserting it in another message.</span></span> <span data-ttu-id="8a29d-111">たとえば、注文書から送付先住所および請求先住所を取得し、請求書に挿入する場合などです。</span><span class="sxs-lookup"><span data-stu-id="8a29d-111">For example, you might take shipping and billing addresses from a purchase order and insert them in an invoice document.</span></span>  
  
 <span data-ttu-id="8a29d-112">BizTalk マッパーでは、独自のグラフィカル システムに基づいたアイコンやリンクを使用して、インスタンス メッセージを出力するための入力インスタンス メッセージの変換 (トランスレートまたはトランスフォーム) を表します。</span><span class="sxs-lookup"><span data-stu-id="8a29d-112">BizTalk Mapper uses its own graphical system of icons and links to represent the translation and transformation of input instance messages to output instance messages.</span></span> <span data-ttu-id="8a29d-113">マッパーで使用されるスキーマのグラフィカル表示は、BizTalk エディターと同じものです。</span><span class="sxs-lookup"><span data-stu-id="8a29d-113">Mapper uses the same graphical representation of schemas as BizTalk Editor.</span></span> <span data-ttu-id="8a29d-114">BizTalk マッパーは、XSLT (Extensible Stylesheet Language Transformations) スタイルシートとしてマップを保存します。</span><span class="sxs-lookup"><span data-stu-id="8a29d-114">BizTalk Mapper stores its maps as Extensible Stylesheet Language Transformations (XSLT) stylesheets.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="8a29d-115">BizTalk マッパーは XSLT 1.0 をサポートします。</span><span class="sxs-lookup"><span data-stu-id="8a29d-115">BizTalk Mapper supports XSLT 1.0.</span></span> <span data-ttu-id="8a29d-116">XSLT 2.0 の使用は、BizTalk マッパーではサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="8a29d-116">Using XSLT 2.0 in BizTalk Mapper is not supported.</span></span>  
  
 <span data-ttu-id="8a29d-117">スキーマの作成方法の詳細については、次を参照してください。 [BizTalk エディターを使用してスキーマを作成する](../core/creating-schemas-using-biztalk-editor.md)です。</span><span class="sxs-lookup"><span data-stu-id="8a29d-117">For information about creating schemas, see [Creating Schemas Using BizTalk Editor](../core/creating-schemas-using-biztalk-editor.md).</span></span> <span data-ttu-id="8a29d-118">オーケストレーション内でマップを使用する方法の詳細については、次を参照してください。[オーケストレーション デザイナーを使用してオーケストレーションを作成する](../core/creating-orchestrations-using-orchestration-designer.md)です。</span><span class="sxs-lookup"><span data-stu-id="8a29d-118">For information about using maps within orchestrations, see [Creating Orchestrations Using Orchestration Designer](../core/creating-orchestrations-using-orchestration-designer.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="8a29d-119">マップのパフォーマンスは、マップの複雑さ (Functoid の数と種類)、入力/出力スキーマのサイズ、入力メッセージのサイズ、およびハードウェアに依存します。</span><span class="sxs-lookup"><span data-stu-id="8a29d-119">The performance of a map depends on the complexity of the map - the number and type of functoids, size of input and output schemas, the size of the input message, and your hardware.</span></span>  
  
 <span data-ttu-id="8a29d-120">BizTalk マッパーのキーボード ショートカットの使用方法の詳細については、次を参照してください。 [BizTalk マッパーのキーボード ショートカット](../core/biztalk-mapper-keyboard-shortcuts.md)です。</span><span class="sxs-lookup"><span data-stu-id="8a29d-120">For information about using the keyboard shortcuts for BizTalk Mapper, see [BizTalk Mapper Keyboard Shortcuts](../core/biztalk-mapper-keyboard-shortcuts.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="8a29d-121">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="8a29d-121">In This Section</span></span>  
  
-   [<span data-ttu-id="8a29d-122">マップを作成する計画</span><span class="sxs-lookup"><span data-stu-id="8a29d-122">Planning to Create Maps</span></span>](../core/planning-to-create-maps.md)  
  
-   [<span data-ttu-id="8a29d-123">マップの概要</span><span class="sxs-lookup"><span data-stu-id="8a29d-123">About Maps</span></span>](../core/about-maps.md)  
  
-   [<span data-ttu-id="8a29d-124">BizTalk マッパーの使用</span><span class="sxs-lookup"><span data-stu-id="8a29d-124">Using BizTalk Mapper</span></span>](../core/using-biztalk-mapper.md)  
  
-   [<span data-ttu-id="8a29d-125">マップを作成します。</span><span class="sxs-lookup"><span data-stu-id="8a29d-125">Creating Maps</span></span>](../core/creating-maps.md)  
  
-   [<span data-ttu-id="8a29d-126">コンパイルして、マップのテスト</span><span class="sxs-lookup"><span data-stu-id="8a29d-126">Compiling and Testing Maps</span></span>](../core/compiling-and-testing-maps.md)  
  
-   [<span data-ttu-id="8a29d-127">マップのトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="8a29d-127">Troubleshooting Maps</span></span>](../core/troubleshooting-maps.md)