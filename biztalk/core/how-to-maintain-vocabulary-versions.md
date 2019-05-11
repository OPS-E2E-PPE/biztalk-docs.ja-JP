---
title: ボキャブラリのバージョンを維持する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- creating, vocabularies
- vocabularies, creating
- vocabularies, versioning
- vocabularies, publishing
- versioning, vocabularies
- updating, vocabularies
- vocabularies, updating
ms.assetid: 43593c6f-4590-4940-ac17-4015928e5838
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7a3049a0e14ad24b31f172a1c49189f968b6dabd
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65384696"
---
# <a name="how-to-maintain-vocabulary-versions"></a><span data-ttu-id="3a91b-102">ボキャブラリのバージョンを維持する方法</span><span class="sxs-lookup"><span data-stu-id="3a91b-102">How to Maintain Vocabulary Versions</span></span>
<span data-ttu-id="3a91b-103">バージョンを保存するには、将来の開発をルール ストアにボキャブラリの定義をボキャブラリのバージョン、追加したとき、またはを追加するユーザーが使用するデータ バインドされた用語の明確に定義された、変更できないセットを作成するバージョンを発行することができます。規則に、ポリシーを開発します。</span><span class="sxs-lookup"><span data-stu-id="3a91b-103">When you have added vocabulary definitions to a version of your vocabulary, you can save the version to the rule store for further development, or you can publish the version to create a well-defined, immutable set of data-bound terms that are available to users to add to rules as they develop their policies.</span></span> <span data-ttu-id="3a91b-104">既存のルールは、古いバージョンを引き続きに指していることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="3a91b-104">Note that fact that existing rules will still point to the old versions.</span></span>  
  
 <span data-ttu-id="3a91b-105">このトピックには、次のタスクの手順が含まれています。</span><span class="sxs-lookup"><span data-stu-id="3a91b-105">This topic contains procedures for the following tasks:</span></span>  
  
-   <span data-ttu-id="3a91b-106">ボキャブラリのバージョンを保存するには</span><span class="sxs-lookup"><span data-stu-id="3a91b-106">To save a vocabulary version</span></span>  
  
-   <span data-ttu-id="3a91b-107">ボキャブラリのバージョンを発行するには</span><span class="sxs-lookup"><span data-stu-id="3a91b-107">To publish a vocabulary version</span></span>  
  
-   <span data-ttu-id="3a91b-108">ボキャブラリの更新バージョンを作成するには</span><span class="sxs-lookup"><span data-stu-id="3a91b-108">To create an updated version of a vocabulary</span></span>  
  
-   <span data-ttu-id="3a91b-109">ボキャブラリの空の新しいバージョンを作成するには</span><span class="sxs-lookup"><span data-stu-id="3a91b-109">To create an empty new version of a vocabulary</span></span>  
  
### <a name="to-save-a-vocabulary-version"></a><span data-ttu-id="3a91b-110">ボキャブラリのバージョンを保存するには</span><span class="sxs-lookup"><span data-stu-id="3a91b-110">To save a vocabulary version</span></span>  
  
-   <span data-ttu-id="3a91b-111">バージョンを右クリックし、クリックして**保存**します。</span><span class="sxs-lookup"><span data-stu-id="3a91b-111">Right-click the version, and then click **Save**.</span></span>  
  
### <a name="to-publish-a-vocabulary-version"></a><span data-ttu-id="3a91b-112">ボキャブラリのバージョンを発行するには</span><span class="sxs-lookup"><span data-stu-id="3a91b-112">To publish a vocabulary version</span></span>  
  
-   <span data-ttu-id="3a91b-113">バージョンを右クリックし、クリックして**発行**します。</span><span class="sxs-lookup"><span data-stu-id="3a91b-113">Right-click the version, and then click **Publish**.</span></span>  
  
### <a name="to-create-an-updated-version-of-a-vocabulary"></a><span data-ttu-id="3a91b-114">ボキャブラリの更新バージョンを作成するには</span><span class="sxs-lookup"><span data-stu-id="3a91b-114">To create an updated version of a vocabulary</span></span>  
  
1.  <span data-ttu-id="3a91b-115">既存のバージョンを右クリックし、をクリックし、**コピー**します。</span><span class="sxs-lookup"><span data-stu-id="3a91b-115">Right-click an existing version, and then click **Copy**.</span></span>  
  
2.  <span data-ttu-id="3a91b-116">ボキャブラリ フォルダーを右クリックし、**貼り付け**します。</span><span class="sxs-lookup"><span data-stu-id="3a91b-116">Right-click the vocabulary folder, and then click **Paste**.</span></span>  
  
     <span data-ttu-id="3a91b-117">コピーされるバージョンと同じ要素を新しいバージョンが作成されます。</span><span class="sxs-lookup"><span data-stu-id="3a91b-117">A new version is created, with the same elements as the copied version.</span></span>  
  
### <a name="to-create-an-empty-new-version-of-a-vocabulary"></a><span data-ttu-id="3a91b-118">ボキャブラリの空の新しいバージョンを作成するには</span><span class="sxs-lookup"><span data-stu-id="3a91b-118">To create an empty new version of a vocabulary</span></span>  
  
-   <span data-ttu-id="3a91b-119">ボキャブラリ フォルダーを右クリックし、**新しいバージョンの追加**します。</span><span class="sxs-lookup"><span data-stu-id="3a91b-119">Right-click the vocabulary folder, and then click **Add New Version**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="3a91b-120">公開済みのボキャブラリのボキャブラリ定義のみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="3a91b-120">You can only use vocabulary definitions from published vocabularies.</span></span>