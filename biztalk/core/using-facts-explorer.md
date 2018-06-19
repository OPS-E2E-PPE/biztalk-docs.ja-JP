---
title: ファクト エクスプ ローラーを使用して |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Business Rule Composer, Facts Explorer
- business rules, vocabularies
- business rules, schemas
- business rules, databases
- business rules, .NET classes
- Facts Explorer [Business Rule Composer]
ms.assetid: ee125eb1-d5b9-4121-8a25-fcb7a640570e
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f4c84b01625bb1566d02c1679bfadd0100b7b406
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22287706"
---
# <a name="using-facts-explorer"></a><span data-ttu-id="48e17-102">ファクト エクスプ ローラーを使用します。</span><span class="sxs-lookup"><span data-stu-id="48e17-102">Using Facts Explorer</span></span>
<span data-ttu-id="48e17-103">ファクト エクスプ ローラーには、4 つのタブが含まれています:**ボキャブラリ**、 **XML スキーマ**、**データベース**、および **.NET クラス**です。</span><span class="sxs-lookup"><span data-stu-id="48e17-103">The Facts Explorer contains four tabs: **Vocabularies**, **XML Schemas**, **Databases**, and **.NET Classes**.</span></span>  
  
## <a name="vocabularies-tab"></a><span data-ttu-id="48e17-104">[ボキャブラリ] タブ</span><span class="sxs-lookup"><span data-stu-id="48e17-104">Vocabularies tab</span></span>  
 <span data-ttu-id="48e17-105">使用して、**ボキャブラリ** タブで、ファクト エクスプ ローラーのボキャブラリのバージョンと定義を管理します。</span><span class="sxs-lookup"><span data-stu-id="48e17-105">Use the **Vocabularies** tab in the Facts Explorer to manage vocabulary versions and definitions.</span></span>  
  
 <span data-ttu-id="48e17-106">ショートカット メニューを使用して、以下のオプションにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="48e17-106">Use the shortcut menu to access the following options.</span></span>  
  
|<span data-ttu-id="48e17-107">プロパティ</span><span class="sxs-lookup"><span data-stu-id="48e17-107">Use this</span></span>|<span data-ttu-id="48e17-108">目的</span><span class="sxs-lookup"><span data-stu-id="48e17-108">To do this</span></span>|  
|--------------|----------------|  
|<span data-ttu-id="48e17-109">**新しいボキャブラリを追加します。**</span><span class="sxs-lookup"><span data-stu-id="48e17-109">**Add New Vocabulary**</span></span>|<span data-ttu-id="48e17-110">新しいボキャブラリを作成します。</span><span class="sxs-lookup"><span data-stu-id="48e17-110">Create a new vocabulary.</span></span>|  
|<span data-ttu-id="48e17-111">**新しいバージョンを追加します。**</span><span class="sxs-lookup"><span data-stu-id="48e17-111">**Add New Version**</span></span>|<span data-ttu-id="48e17-112">選択したボキャブラリの新しい空のバージョンを作成します。</span><span class="sxs-lookup"><span data-stu-id="48e17-112">Create a new empty version of the selected vocabulary.</span></span> <span data-ttu-id="48e17-113">他のバージョンから定義をコピーし、新しいバージョンに貼り付けることができます。</span><span class="sxs-lookup"><span data-stu-id="48e17-113">You can copy definitions from other versions and paste them into the new version.</span></span>|  
|<span data-ttu-id="48e17-114">**ボキャブラリのバージョンの貼り付け**</span><span class="sxs-lookup"><span data-stu-id="48e17-114">**Paste Vocabulary Version**</span></span>|<span data-ttu-id="48e17-115">前にコピーしたボキャブラリのバージョンの内容を、選択したボキャブラリに新しいバージョンとして貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="48e17-115">Paste the contents of a previously copied vocabulary version as a new version in the selected vocabulary.</span></span>|  
|<span data-ttu-id="48e17-116">**Del**</span><span class="sxs-lookup"><span data-stu-id="48e17-116">**Delete**</span></span>|<span data-ttu-id="48e17-117">選択したボキャブラリとすべてのバージョンを削除します。</span><span class="sxs-lookup"><span data-stu-id="48e17-117">Delete the selected vocabulary and all its versions.</span></span>|  
|<span data-ttu-id="48e17-118">**新しい定義を追加します。**</span><span class="sxs-lookup"><span data-stu-id="48e17-118">**Add New Definition**</span></span>|<span data-ttu-id="48e17-119">ボキャブラリの定義ウィザードを起動して、選択したボキャブラリのバージョンに新しい定義を作成します。</span><span class="sxs-lookup"><span data-stu-id="48e17-119">Launch the Vocabulary Definition Wizard to create a new definition in the selected vocabulary version.</span></span>|  
|<span data-ttu-id="48e17-120">**および**</span><span class="sxs-lookup"><span data-stu-id="48e17-120">**Save**</span></span>|<span data-ttu-id="48e17-121">選択したバージョンと定義に加えた変更を保存します。</span><span class="sxs-lookup"><span data-stu-id="48e17-121">Save the changes made to the selected version and its definitions.</span></span>|  
|<span data-ttu-id="48e17-122">**発行**</span><span class="sxs-lookup"><span data-stu-id="48e17-122">**Publish**</span></span>|<span data-ttu-id="48e17-123">選択したボキャブラリのバージョンを公開します。</span><span class="sxs-lookup"><span data-stu-id="48e17-123">Publish the selected vocabulary version.</span></span> <span data-ttu-id="48e17-124">公開済みのバージョンは直接変更できないことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="48e17-124">Note that you cannot directly modify a published version.</span></span> <span data-ttu-id="48e17-125">公開済みのバージョンをコピーして、そのボキャブラリの新しいバージョンに貼り付けることができます。</span><span class="sxs-lookup"><span data-stu-id="48e17-125">You can copy and paste it to a new version of the vocabulary.</span></span>|  
|<span data-ttu-id="48e17-126">**再読み込み**</span><span class="sxs-lookup"><span data-stu-id="48e17-126">**Reload**</span></span>|<span data-ttu-id="48e17-127">選択したボキャブラリのバージョンと定義を再読み込みします。バージョンに加えた作業中の変更を破棄し、ルール ストアからその内容を復元することもできます。</span><span class="sxs-lookup"><span data-stu-id="48e17-127">Reload the selected vocabulary version and its definitions, with the option to discard any current changes made in that version and restore the contents from the rule store.</span></span>|  
|<span data-ttu-id="48e17-128">**変更**</span><span class="sxs-lookup"><span data-stu-id="48e17-128">**Modify**</span></span>|<span data-ttu-id="48e17-129">ボキャブラリの定義ウィザードを起動して、選択した定義を変更します。</span><span class="sxs-lookup"><span data-stu-id="48e17-129">Launch the Vocabulary Definition Wizard to change the selected definition.</span></span> <span data-ttu-id="48e17-130">公開済みのボキャブラリのバージョンに含まれている定義は変更できないことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="48e17-130">Note that you cannot modify a definition that is part of a published vocabulary version.</span></span>|  
|<span data-ttu-id="48e17-131">**ソース ファクトに移動します。**</span><span class="sxs-lookup"><span data-stu-id="48e17-131">**Go to source fact**</span></span>|<span data-ttu-id="48e17-132">選択した定義の、.NET アセンブリ、XML スキーマ、またはデータベース テーブル内の対応するソース ファクトに移動します。</span><span class="sxs-lookup"><span data-stu-id="48e17-132">For the selected definition, go to the corresponding source fact in a .NET assembly, XML schema, or database table.</span></span>|  
  
## <a name="xml-schemas-tab"></a><span data-ttu-id="48e17-133">[XML スキーマ] タブ</span><span class="sxs-lookup"><span data-stu-id="48e17-133">XML Schemas tab</span></span>  
 <span data-ttu-id="48e17-134">XSD スキーマから XML 要素と XML 属性の定義を参照します。</span><span class="sxs-lookup"><span data-stu-id="48e17-134">Browse through XSD schemas for the definitions of XML elements and attributes.</span></span> <span data-ttu-id="48e17-135">アイテムを未公開のボキャブラリのバージョンにドラッグできるよう、**ボキャブラリ** タブの定義を作成または述語、アクション、および引数を定義するには、条件エディターまたはアクション エディターにアイテムをドラッグすることができます。</span><span class="sxs-lookup"><span data-stu-id="48e17-135">You can drag items onto unpublished vocabulary versions on the **Vocabulary** tab to create definitions, or you can drag items to the Conditions Editor or Actions Editor to define predicates, actions, and arguments.</span></span>  
  
|<span data-ttu-id="48e17-136">プロパティ</span><span class="sxs-lookup"><span data-stu-id="48e17-136">Use this</span></span>|<span data-ttu-id="48e17-137">目的</span><span class="sxs-lookup"><span data-stu-id="48e17-137">To do this</span></span>|  
|--------------|----------------|  
|<span data-ttu-id="48e17-138">**ルート ノードを選択します。**</span><span class="sxs-lookup"><span data-stu-id="48e17-138">**Select Root Node**</span></span>|<span data-ttu-id="48e17-139">複数のルート ノードを含む XML スキーマから読み込まれるルート ノードを選択します。</span><span class="sxs-lookup"><span data-stu-id="48e17-139">Select a root node to load from an XML schema that contains multiple root notes.</span></span>|  
  
## <a name="databases-tab"></a><span data-ttu-id="48e17-140">[データベース] タブ</span><span class="sxs-lookup"><span data-stu-id="48e17-140">Databases tab</span></span>  
 <span data-ttu-id="48e17-141">データベースおよびテーブル定義用のデータベース サーバーを参照します。</span><span class="sxs-lookup"><span data-stu-id="48e17-141">Browse through database servers for databases and table definitions.</span></span> <span data-ttu-id="48e17-142">アイテムを未公開のボキャブラリのバージョンにドラッグできるよう、**ボキャブラリ** タブの定義を作成または述語、アクション、および引数を定義するには、条件エディターまたはアクション エディターにアイテムをドラッグすることができます。</span><span class="sxs-lookup"><span data-stu-id="48e17-142">You can drag items onto unpublished vocabulary versions on the **Vocabulary** tab to create definitions, or you can drag items to the Conditions Editor or Actions Editor to define predicates, actions, and arguments.</span></span>  
  
## <a name="net-classes-tab"></a><span data-ttu-id="48e17-143">[.NET クラス] タブ</span><span class="sxs-lookup"><span data-stu-id="48e17-143">.NET Classes tab</span></span>  
 <span data-ttu-id="48e17-144">パブリック .NET クラス定義の .NET アセンブリを参照します。</span><span class="sxs-lookup"><span data-stu-id="48e17-144">Browse through .NET assemblies for public .NET class definitions.</span></span> <span data-ttu-id="48e17-145">アイテムを未公開のボキャブラリのバージョンにドラッグできるよう、**ボキャブラリ** タブの定義を作成または述語、アクション、および引数を定義するには、条件エディターまたはアクション エディターにアイテムをドラッグすることができます。</span><span class="sxs-lookup"><span data-stu-id="48e17-145">You can drag items onto unpublished vocabulary versions on the **Vocabulary** tab to create definitions, or you can drag items to the Conditions Editor or Actions Editor to define predicates, actions, and arguments.</span></span>  
  
|<span data-ttu-id="48e17-146">プロパティ</span><span class="sxs-lookup"><span data-stu-id="48e17-146">Use this</span></span>|<span data-ttu-id="48e17-147">目的</span><span class="sxs-lookup"><span data-stu-id="48e17-147">To do this</span></span>|  
|--------------|----------------|  
|<span data-ttu-id="48e17-148">**参照**</span><span class="sxs-lookup"><span data-stu-id="48e17-148">**Browse**</span></span>|<span data-ttu-id="48e17-149">グローバル アセンブリ キャッシュから .NET アセンブリを読み込みます。</span><span class="sxs-lookup"><span data-stu-id="48e17-149">Load a .NET assembly from the global assembly cache</span></span>|  
|<span data-ttu-id="48e17-150">**[削除]**</span><span class="sxs-lookup"><span data-stu-id="48e17-150">**Remove**</span></span>|<span data-ttu-id="48e17-151">.NET アセンブリを削除します。</span><span class="sxs-lookup"><span data-stu-id="48e17-151">Remove a .NET assembly</span></span>|