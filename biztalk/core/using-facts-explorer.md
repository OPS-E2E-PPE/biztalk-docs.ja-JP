---
title: ファクト エクスプ ローラーを使用して |Microsoft Docs
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
ms.openlocfilehash: 79020dd4487d338e839a4a6d7bacc815f2b19bf9
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65247330"
---
# <a name="using-facts-explorer"></a><span data-ttu-id="bf462-102">ファクト エクスプ ローラーを使用します。</span><span class="sxs-lookup"><span data-stu-id="bf462-102">Using Facts Explorer</span></span>
<span data-ttu-id="bf462-103">ファクト エクスプ ローラーには、4 つのタブが含まれています。**ボキャブラリ**、 **XML スキーマ**、**データベース**、および **.NET クラス**します。</span><span class="sxs-lookup"><span data-stu-id="bf462-103">The Facts Explorer contains four tabs: **Vocabularies**, **XML Schemas**, **Databases**, and **.NET Classes**.</span></span>  
  
## <a name="vocabularies-tab"></a><span data-ttu-id="bf462-104">ボキャブラリ タブ</span><span class="sxs-lookup"><span data-stu-id="bf462-104">Vocabularies tab</span></span>  
 <span data-ttu-id="bf462-105">使用して、**ボキャブラリ** タブで、ファクト エクスプ ローラーのボキャブラリのバージョンと定義を管理します。</span><span class="sxs-lookup"><span data-stu-id="bf462-105">Use the **Vocabularies** tab in the Facts Explorer to manage vocabulary versions and definitions.</span></span>  
  
 <span data-ttu-id="bf462-106">次のオプションにアクセスするのにには、ショートカット メニューを使用します。</span><span class="sxs-lookup"><span data-stu-id="bf462-106">Use the shortcut menu to access the following options.</span></span>  
  
|<span data-ttu-id="bf462-107">プロパティ</span><span class="sxs-lookup"><span data-stu-id="bf462-107">Use this</span></span>|<span data-ttu-id="bf462-108">目的</span><span class="sxs-lookup"><span data-stu-id="bf462-108">To do this</span></span>|  
|--------------|----------------|  
|<span data-ttu-id="bf462-109">**新しいボキャブラリを追加します。**</span><span class="sxs-lookup"><span data-stu-id="bf462-109">**Add New Vocabulary**</span></span>|<span data-ttu-id="bf462-110">新しいボキャブラリを作成します。</span><span class="sxs-lookup"><span data-stu-id="bf462-110">Create a new vocabulary.</span></span>|  
|<span data-ttu-id="bf462-111">**新しいバージョンを追加します。**</span><span class="sxs-lookup"><span data-stu-id="bf462-111">**Add New Version**</span></span>|<span data-ttu-id="bf462-112">選択したボキャブラリの新しい空のバージョンを作成します。</span><span class="sxs-lookup"><span data-stu-id="bf462-112">Create a new empty version of the selected vocabulary.</span></span> <span data-ttu-id="bf462-113">その他のバージョンから定義をコピーして、新しいバージョンに貼り付けることです。</span><span class="sxs-lookup"><span data-stu-id="bf462-113">You can copy definitions from other versions and paste them into the new version.</span></span>|  
|<span data-ttu-id="bf462-114">**ボキャブラリのバージョンの貼り付け**</span><span class="sxs-lookup"><span data-stu-id="bf462-114">**Paste Vocabulary Version**</span></span>|<span data-ttu-id="bf462-115">選択したボキャブラリの新しいバージョンとして以前にコピーしたボキャブラリのバージョンの内容を貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="bf462-115">Paste the contents of a previously copied vocabulary version as a new version in the selected vocabulary.</span></span>|  
|<span data-ttu-id="bf462-116">**削除**</span><span class="sxs-lookup"><span data-stu-id="bf462-116">**Delete**</span></span>|<span data-ttu-id="bf462-117">選択したボキャブラリとすべてのバージョンを削除します。</span><span class="sxs-lookup"><span data-stu-id="bf462-117">Delete the selected vocabulary and all its versions.</span></span>|  
|<span data-ttu-id="bf462-118">**新しい定義を追加します。**</span><span class="sxs-lookup"><span data-stu-id="bf462-118">**Add New Definition**</span></span>|<span data-ttu-id="bf462-119">選択したボキャブラリのバージョンで、新しい定義を作成するボキャブラリの定義ウィザードを起動します。</span><span class="sxs-lookup"><span data-stu-id="bf462-119">Launch the Vocabulary Definition Wizard to create a new definition in the selected vocabulary version.</span></span>|  
|<span data-ttu-id="bf462-120">**および**</span><span class="sxs-lookup"><span data-stu-id="bf462-120">**Save**</span></span>|<span data-ttu-id="bf462-121">選択したバージョンとその定義に加えられた変更を保存します。</span><span class="sxs-lookup"><span data-stu-id="bf462-121">Save the changes made to the selected version and its definitions.</span></span>|  
|<span data-ttu-id="bf462-122">**発行**</span><span class="sxs-lookup"><span data-stu-id="bf462-122">**Publish**</span></span>|<span data-ttu-id="bf462-123">選択したボキャブラリのバージョンを公開します。</span><span class="sxs-lookup"><span data-stu-id="bf462-123">Publish the selected vocabulary version.</span></span> <span data-ttu-id="bf462-124">公開されたバージョンを直接変更できないことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="bf462-124">Note that you cannot directly modify a published version.</span></span> <span data-ttu-id="bf462-125">コピーし、ボキャブラリの新しいバージョンに貼り付けることができます。</span><span class="sxs-lookup"><span data-stu-id="bf462-125">You can copy and paste it to a new version of the vocabulary.</span></span>|  
|<span data-ttu-id="bf462-126">**再読み込み**</span><span class="sxs-lookup"><span data-stu-id="bf462-126">**Reload**</span></span>|<span data-ttu-id="bf462-127">選択したボキャブラリのバージョンと現在のバージョンに加えた変更を破棄するオプションを使用して、定義を再読み込みし、ルール ストアから内容を復元します。</span><span class="sxs-lookup"><span data-stu-id="bf462-127">Reload the selected vocabulary version and its definitions, with the option to discard any current changes made in that version and restore the contents from the rule store.</span></span>|  
|<span data-ttu-id="bf462-128">**Modify**</span><span class="sxs-lookup"><span data-stu-id="bf462-128">**Modify**</span></span>|<span data-ttu-id="bf462-129">選択した定義を変更するボキャブラリの定義ウィザードを起動します。</span><span class="sxs-lookup"><span data-stu-id="bf462-129">Launch the Vocabulary Definition Wizard to change the selected definition.</span></span> <span data-ttu-id="bf462-130">公開済みのボキャブラリのバージョンの一部である定義を変更できないことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="bf462-130">Note that you cannot modify a definition that is part of a published vocabulary version.</span></span>|  
|<span data-ttu-id="bf462-131">**ソース ファクトに移動します。**</span><span class="sxs-lookup"><span data-stu-id="bf462-131">**Go to source fact**</span></span>|<span data-ttu-id="bf462-132">選択した定義は、.NET アセンブリ、XML スキーマ、またはデータベース テーブル内の対応するソース ファクトを参照してください。</span><span class="sxs-lookup"><span data-stu-id="bf462-132">For the selected definition, go to the corresponding source fact in a .NET assembly, XML schema, or database table.</span></span>|  
  
## <a name="xml-schemas-tab"></a><span data-ttu-id="bf462-133">XML スキーマ タブ</span><span class="sxs-lookup"><span data-stu-id="bf462-133">XML Schemas tab</span></span>  
 <span data-ttu-id="bf462-134">XSD スキーマの XML 要素と属性の定義を参照します。</span><span class="sxs-lookup"><span data-stu-id="bf462-134">Browse through XSD schemas for the definitions of XML elements and attributes.</span></span> <span data-ttu-id="bf462-135">未公開のボキャブラリのバージョンに項目をドラッグできるよう、**ボキャブラリ**定義を作成 タブまたは述語、アクション、および引数を定義するには、条件エディターまたはアクション エディターに項目をドラッグすることができます。</span><span class="sxs-lookup"><span data-stu-id="bf462-135">You can drag items onto unpublished vocabulary versions on the **Vocabulary** tab to create definitions, or you can drag items to the Conditions Editor or Actions Editor to define predicates, actions, and arguments.</span></span>  
  
|<span data-ttu-id="bf462-136">プロパティ</span><span class="sxs-lookup"><span data-stu-id="bf462-136">Use this</span></span>|<span data-ttu-id="bf462-137">目的</span><span class="sxs-lookup"><span data-stu-id="bf462-137">To do this</span></span>|  
|--------------|----------------|  
|<span data-ttu-id="bf462-138">**ルート ノードを選択します。**</span><span class="sxs-lookup"><span data-stu-id="bf462-138">**Select Root Node**</span></span>|<span data-ttu-id="bf462-139">複数のルート ノードを含む XML スキーマからの読み込みにルート ノードを選択します。</span><span class="sxs-lookup"><span data-stu-id="bf462-139">Select a root node to load from an XML schema that contains multiple root notes.</span></span>|  
  
## <a name="databases-tab"></a><span data-ttu-id="bf462-140">[データベース] タブ</span><span class="sxs-lookup"><span data-stu-id="bf462-140">Databases tab</span></span>  
 <span data-ttu-id="bf462-141">データベースとテーブル定義用のデータベース サーバーを参照します。</span><span class="sxs-lookup"><span data-stu-id="bf462-141">Browse through database servers for databases and table definitions.</span></span> <span data-ttu-id="bf462-142">未公開のボキャブラリのバージョンに項目をドラッグできるよう、**ボキャブラリ**定義を作成 タブまたは述語、アクション、および引数を定義するには、条件エディターまたはアクション エディターに項目をドラッグすることができます。</span><span class="sxs-lookup"><span data-stu-id="bf462-142">You can drag items onto unpublished vocabulary versions on the **Vocabulary** tab to create definitions, or you can drag items to the Conditions Editor or Actions Editor to define predicates, actions, and arguments.</span></span>  
  
## <a name="net-classes-tab"></a><span data-ttu-id="bf462-143">.NET クラス タブ</span><span class="sxs-lookup"><span data-stu-id="bf462-143">.NET Classes tab</span></span>  
 <span data-ttu-id="bf462-144">パブリック .NET クラス定義の .NET アセンブリを参照します。</span><span class="sxs-lookup"><span data-stu-id="bf462-144">Browse through .NET assemblies for public .NET class definitions.</span></span> <span data-ttu-id="bf462-145">未公開のボキャブラリのバージョンに項目をドラッグできるよう、**ボキャブラリ**定義を作成 タブまたは述語、アクション、および引数を定義するには、条件エディターまたはアクション エディターに項目をドラッグすることができます。</span><span class="sxs-lookup"><span data-stu-id="bf462-145">You can drag items onto unpublished vocabulary versions on the **Vocabulary** tab to create definitions, or you can drag items to the Conditions Editor or Actions Editor to define predicates, actions, and arguments.</span></span>  
  
|<span data-ttu-id="bf462-146">プロパティ</span><span class="sxs-lookup"><span data-stu-id="bf462-146">Use this</span></span>|<span data-ttu-id="bf462-147">目的</span><span class="sxs-lookup"><span data-stu-id="bf462-147">To do this</span></span>|  
|--------------|----------------|  
|<span data-ttu-id="bf462-148">**[参照]**</span><span class="sxs-lookup"><span data-stu-id="bf462-148">**Browse**</span></span>|<span data-ttu-id="bf462-149">グローバル アセンブリ キャッシュから .NET アセンブリを読み込む</span><span class="sxs-lookup"><span data-stu-id="bf462-149">Load a .NET assembly from the global assembly cache</span></span>|  
|<span data-ttu-id="bf462-150">**[削除]**</span><span class="sxs-lookup"><span data-stu-id="bf462-150">**Remove**</span></span>|<span data-ttu-id="bf462-151">.NET アセンブリを削除します。</span><span class="sxs-lookup"><span data-stu-id="bf462-151">Remove a .NET assembly</span></span>|