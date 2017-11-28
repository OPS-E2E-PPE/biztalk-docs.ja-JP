---
title: "ボキャブラリを作成する方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- creating, vocabularies
- vocabularies, business rules
- business rules, vocabularies
- vocabularies, creating
ms.assetid: 5c16eb98-2257-44f2-8a29-899e02f7e556
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2644cc938cbe5e42f4e124453d863741755d965d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-develop-vocabularies"></a><span data-ttu-id="0d848-102">ボキャブラリを作成する方法</span><span class="sxs-lookup"><span data-stu-id="0d848-102">How to Develop Vocabularies</span></span>
<span data-ttu-id="0d848-103">ルールの条件とアクションには、送信元に基づくバインド情報が使用されるため、このバインド情報が何を指しているのか、ユーザーにわかるよう明確に定義されていることが大切です。</span><span class="sxs-lookup"><span data-stu-id="0d848-103">Rule conditions and actions are based on sources that may have detailed, difficult-to-read binding information that tells the user little or nothing about what they refer to.</span></span> <span data-ttu-id="0d848-104">ビジネス ルール フレームワークでは、ボキャブラリを作成することによって、ユーザーがルールの条件とアクションを明確に理解できるような直観的かつドメイン固有の用語を定義し、ルールの開発プロセスを効率化できます。</span><span class="sxs-lookup"><span data-stu-id="0d848-104">The Business Rules Framework enables you to create vocabularies to simplify the development of rules by offering users intuitive, domain-specific terminology that users can associate with rule conditions and actions.</span></span>  
  
 <span data-ttu-id="0d848-105">使用するデータ ソースを明確に区別できるほか、新しいボキャブラリを作成したり、そこにボキャブラリ定義を追加することもできます。</span><span class="sxs-lookup"><span data-stu-id="0d848-105">You can identify data sources to use, create a new vocabulary, and add vocabulary definitions to it.</span></span> <span data-ttu-id="0d848-106">ボキャブラリのバージョンをルール ストアに保存しておき、準備が整った段階で、それを公開することによって、ユーザーはデータと用語との関連性を確実に把握できるようになります。</span><span class="sxs-lookup"><span data-stu-id="0d848-106">You can save a version of your vocabulary to the rule store, and when it is complete, you can publish it to provide users with a well-defined, immutable set of terms that are bound to data references.</span></span>  
  
 <span data-ttu-id="0d848-107">将来ボキャブラリに修正が必要となった場合は、変更内容を反映した新しいボキャブラリ バージョンを作成するだけで済みます。</span><span class="sxs-lookup"><span data-stu-id="0d848-107">If you need to make changes to your vocabulary in the future, you can simply create a new version of the vocabulary that reflects the changes.</span></span>  
  
> [!CAUTION]
>  <span data-ttu-id="0d848-108">新しいボキャブラリ バージョンを作成しても、既存のボキャブラリを基に作成されたルールは、依然として古いほうのバージョンを参照します。</span><span class="sxs-lookup"><span data-stu-id="0d848-108">When a new version of a vocabulary is created, the rules built from a previous version will still point to the previous version.</span></span>  
  
### <a name="to-create-a-vocabulary"></a><span data-ttu-id="0d848-109">新しいボキャブラリを作成するには</span><span class="sxs-lookup"><span data-stu-id="0d848-109">To create a vocabulary</span></span>  
  
1.  <span data-ttu-id="0d848-110">[ファクト エクスプ ローラー] ウィンドウ、**ボキャブラリ**タブです。</span><span class="sxs-lookup"><span data-stu-id="0d848-110">In the Facts Explorer window, click the **Vocabularies** tab.</span></span>  
  
2.  <span data-ttu-id="0d848-111">右クリックし、**ボキャブラリ**フォルダー、およびクリック**新しいボキャブラリの追加**です。</span><span class="sxs-lookup"><span data-stu-id="0d848-111">Right-click the **Vocabularies** folder, and then click **Add New Vocabulary**.</span></span>  
  
     <span data-ttu-id="0d848-112">新しい**ボキャブラリ**下のフォルダーに表示されます、**ボキャブラリ**フォルダーです。</span><span class="sxs-lookup"><span data-stu-id="0d848-112">A new **vocabulary** folder appears under the **Vocabularies** folder.</span></span>  
  
3.  <span data-ttu-id="0d848-113">クリックして、新しい**ボキャブラリ**フォルダー、および [プロパティ] ウィンドウ内の名前を編集します。</span><span class="sxs-lookup"><span data-stu-id="0d848-113">Click the new **vocabulary** folder, and then edit the name in the Properties window.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="0d848-114">ボキャブラリまたはポリシーの名前を変更するには、すべてのバージョンの定義が保存されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="0d848-114">You must save everything (all versions of the definitions) before you can rename a vocabulary or a policy.</span></span>