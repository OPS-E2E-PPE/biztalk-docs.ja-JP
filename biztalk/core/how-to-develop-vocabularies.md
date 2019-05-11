---
title: ボキャブラリを作成する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- creating, vocabularies
- vocabularies, business rules
- business rules, vocabularies
- vocabularies, creating
ms.assetid: 5c16eb98-2257-44f2-8a29-899e02f7e556
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1aac6d9350b3f93df3755b3b082db9e8e5ab7f6f
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65338427"
---
# <a name="how-to-develop-vocabularies"></a><span data-ttu-id="83987-102">ボキャブラリを作成する方法</span><span class="sxs-lookup"><span data-stu-id="83987-102">How to Develop Vocabularies</span></span>
<span data-ttu-id="83987-103">ルール条件およびアクションは、詳細な可能性があります、ユーザーのほとんど、またはを参照しているところを示す読み取り困難なバインド情報ソースに基づいています。</span><span class="sxs-lookup"><span data-stu-id="83987-103">Rule conditions and actions are based on sources that may have detailed, difficult-to-read binding information that tells the user little or nothing about what they refer to.</span></span> <span data-ttu-id="83987-104">ビジネス ルール フレームワークでは、ユーザーは、ルール条件およびアクションに関連付けることが、直感的なドメイン固有の用語をユーザーに提供することで、ルールの開発を簡略化するボキャブラリを作成することができます。</span><span class="sxs-lookup"><span data-stu-id="83987-104">The Business Rules Framework enables you to create vocabularies to simplify the development of rules by offering users intuitive, domain-specific terminology that users can associate with rule conditions and actions.</span></span>  
  
 <span data-ttu-id="83987-105">使用して、新しいボキャブラリを作成するデータ ソースを特定し、ボキャブラリの定義を追加することができます。</span><span class="sxs-lookup"><span data-stu-id="83987-105">You can identify data sources to use, create a new vocabulary, and add vocabulary definitions to it.</span></span> <span data-ttu-id="83987-106">ボキャブラリのバージョンを保存するにはルール ストアへとそれが完了したら、ユーザー データの参照にバインドされている用語の明確に定義された、変更できないセットを提供することを発行できます。</span><span class="sxs-lookup"><span data-stu-id="83987-106">You can save a version of your vocabulary to the rule store, and when it is complete, you can publish it to provide users with a well-defined, immutable set of terms that are bound to data references.</span></span>  
  
 <span data-ttu-id="83987-107">今後のボキャブラリを変更する必要がある場合だけ、変更を反映するボキャブラリの新しいバージョンを作成できます。</span><span class="sxs-lookup"><span data-stu-id="83987-107">If you need to make changes to your vocabulary in the future, you can simply create a new version of the vocabulary that reflects the changes.</span></span>  
  
> [!CAUTION]
>  <span data-ttu-id="83987-108">ボキャブラリの新しいバージョンが作成されると、以前のバージョンから構築されている規則は引き続き 以前のバージョンを指します。</span><span class="sxs-lookup"><span data-stu-id="83987-108">When a new version of a vocabulary is created, the rules built from a previous version will still point to the previous version.</span></span>  
  
### <a name="to-create-a-vocabulary"></a><span data-ttu-id="83987-109">ボキャブラリを作成するには</span><span class="sxs-lookup"><span data-stu-id="83987-109">To create a vocabulary</span></span>  
  
1.  <span data-ttu-id="83987-110">[ファクト エクスプ ローラー] ウィンドウ、**ボキャブラリ**タブ。</span><span class="sxs-lookup"><span data-stu-id="83987-110">In the Facts Explorer window, click the **Vocabularies** tab.</span></span>  
  
2.  <span data-ttu-id="83987-111">右クリックし、**ボキャブラリ**フォルダー、およびクリック**新しいボキャブラリの追加**します。</span><span class="sxs-lookup"><span data-stu-id="83987-111">Right-click the **Vocabularies** folder, and then click **Add New Vocabulary**.</span></span>  
  
     <span data-ttu-id="83987-112">新しい**ボキャブラリ**下のフォルダーに表示されます、**ボキャブラリ**フォルダー。</span><span class="sxs-lookup"><span data-stu-id="83987-112">A new **vocabulary** folder appears under the **Vocabularies** folder.</span></span>  
  
3.  <span data-ttu-id="83987-113">[新規] をクリックして**ボキャブラリ**フォルダー、および [プロパティ] ウィンドウで名前を編集します。</span><span class="sxs-lookup"><span data-stu-id="83987-113">Click the new **vocabulary** folder, and then edit the name in the Properties window.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="83987-114">ポリシーまたはボキャブラリの名前を変更する前に、すべてのもの (定義のすべてのバージョン) を保存する必要があります。</span><span class="sxs-lookup"><span data-stu-id="83987-114">You must save everything (all versions of the definitions) before you can rename a vocabulary or a policy.</span></span>