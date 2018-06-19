---
title: ボキャブラリのバージョンを維持する方法 |Microsoft ドキュメント
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
ms.openlocfilehash: 1b3c67d79878c59e3b0dcba6dcd15955f34ad97c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22254370"
---
# <a name="how-to-maintain-vocabulary-versions"></a><span data-ttu-id="bf15f-102">ボキャブラリのバージョンを維持する方法</span><span class="sxs-lookup"><span data-stu-id="bf15f-102">How to Maintain Vocabulary Versions</span></span>
<span data-ttu-id="bf15f-103">ボキャブラリの定義をボキャブラリのバージョンに追加することにより、将来の開発に備えて特定のバージョンをルール ストアに保存できます。また、そのバージョンを公開して、厳密に定義されたデータ関連の用語のセットを作成し、ポリシーを作成する際に、これらの用語をルールに追加することができます。</span><span class="sxs-lookup"><span data-stu-id="bf15f-103">When you have added vocabulary definitions to a version of your vocabulary, you can save the version to the rule store for further development, or you can publish the version to create a well-defined, immutable set of data-bound terms that are available to users to add to rules as they develop their policies.</span></span> <span data-ttu-id="bf15f-104">ただし、ボキャブラリをバージョンに追加したとしても、既存のルールでは、古いバージョンが参照される点に注意してください。</span><span class="sxs-lookup"><span data-stu-id="bf15f-104">Note that fact that existing rules will still point to the old versions.</span></span>  
  
 <span data-ttu-id="bf15f-105">このトピックでは、次の操作の手順について説明します。</span><span class="sxs-lookup"><span data-stu-id="bf15f-105">This topic contains procedures for the following tasks:</span></span>  
  
-   <span data-ttu-id="bf15f-106">ボキャブラリのバージョンを保存するには</span><span class="sxs-lookup"><span data-stu-id="bf15f-106">To save a vocabulary version</span></span>  
  
-   <span data-ttu-id="bf15f-107">ボキャブラリのバージョンを公開するには</span><span class="sxs-lookup"><span data-stu-id="bf15f-107">To publish a vocabulary version</span></span>  
  
-   <span data-ttu-id="bf15f-108">既存のボキャブラリ バージョンをコピーするには</span><span class="sxs-lookup"><span data-stu-id="bf15f-108">To create an updated version of a vocabulary</span></span>  
  
-   <span data-ttu-id="bf15f-109">ボキャブラリの空のバージョンを新規作成するには</span><span class="sxs-lookup"><span data-stu-id="bf15f-109">To create an empty new version of a vocabulary</span></span>  
  
### <a name="to-save-a-vocabulary-version"></a><span data-ttu-id="bf15f-110">ボキャブラリのバージョンを保存するには</span><span class="sxs-lookup"><span data-stu-id="bf15f-110">To save a vocabulary version</span></span>  
  
-   <span data-ttu-id="bf15f-111">バージョンを右クリックし、をクリックして**保存**です。</span><span class="sxs-lookup"><span data-stu-id="bf15f-111">Right-click the version, and then click **Save**.</span></span>  
  
### <a name="to-publish-a-vocabulary-version"></a><span data-ttu-id="bf15f-112">ボキャブラリのバージョンを公開するには</span><span class="sxs-lookup"><span data-stu-id="bf15f-112">To publish a vocabulary version</span></span>  
  
-   <span data-ttu-id="bf15f-113">バージョンを右クリックし、をクリックして**発行**です。</span><span class="sxs-lookup"><span data-stu-id="bf15f-113">Right-click the version, and then click **Publish**.</span></span>  
  
### <a name="to-create-an-updated-version-of-a-vocabulary"></a><span data-ttu-id="bf15f-114">既存のボキャブラリ バージョンをコピーするには</span><span class="sxs-lookup"><span data-stu-id="bf15f-114">To create an updated version of a vocabulary</span></span>  
  
1.  <span data-ttu-id="bf15f-115">既存のバージョンを右クリックし、をクリックして**コピー**です。</span><span class="sxs-lookup"><span data-stu-id="bf15f-115">Right-click an existing version, and then click **Copy**.</span></span>  
  
2.  <span data-ttu-id="bf15f-116">ボキャブラリ フォルダーを右クリックし、をクリックして**貼り付け**です。</span><span class="sxs-lookup"><span data-stu-id="bf15f-116">Right-click the vocabulary folder, and then click **Paste**.</span></span>  
  
     <span data-ttu-id="bf15f-117">コピー元と同じ要素を持つ新しいバージョンが作成されます。</span><span class="sxs-lookup"><span data-stu-id="bf15f-117">A new version is created, with the same elements as the copied version.</span></span>  
  
### <a name="to-create-an-empty-new-version-of-a-vocabulary"></a><span data-ttu-id="bf15f-118">ボキャブラリの空のバージョンを新規作成するには</span><span class="sxs-lookup"><span data-stu-id="bf15f-118">To create an empty new version of a vocabulary</span></span>  
  
-   <span data-ttu-id="bf15f-119">ボキャブラリ フォルダーを右クリックし、をクリックして**新しいバージョンの追加**です。</span><span class="sxs-lookup"><span data-stu-id="bf15f-119">Right-click the vocabulary folder, and then click **Add New Version**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="bf15f-120">公開されたボキャブラリの定義しか使用できません。</span><span class="sxs-lookup"><span data-stu-id="bf15f-120">You can only use vocabulary definitions from published vocabularies.</span></span>