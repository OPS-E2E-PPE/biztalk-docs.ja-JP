---
title: "ボキャブラリの定義を作成する方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- creating, vocabularies
- vocabularies, creating
- vocabularies, definitions
ms.assetid: 6f8fc4c2-2c46-4a7d-a02f-89de0396e3e2
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ff9fdfc7cd444a97d1a24353c13d93460c00d4ba
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-create-vocabulary-definitions"></a><span data-ttu-id="139a2-102">ボキャブラリの定義を作成する方法</span><span class="sxs-lookup"><span data-stu-id="139a2-102">How to Create Vocabulary Definitions</span></span>
<span data-ttu-id="139a2-103">ボキャブラリの定義ウィザードを使用して、ボキャブラリの定義を作成できます。</span><span class="sxs-lookup"><span data-stu-id="139a2-103">You can use the Vocabulary Definition Wizard to create vocabulary definitions.</span></span> <span data-ttu-id="139a2-104">ボキャブラリの定義は、定数値、値の範囲、値セット、または .NET アセンブリ、XML ドキュメント、データベース テーブルの要素として定義できます。</span><span class="sxs-lookup"><span data-stu-id="139a2-104">You can define a vocabulary definition as a constant value, a range of values, a set of values, or elements of a .NET assembly, XML document, or database table.</span></span> <span data-ttu-id="139a2-105">パブリック変数を選択する場合があります**取得**と**設定**オプションと同様に、データベースおよび XML の定義ウィザード。</span><span class="sxs-lookup"><span data-stu-id="139a2-105">If you select a public variable, there will be **Get** and **Set** options just like in Database and XML definition wizard.</span></span>  
  
 <span data-ttu-id="139a2-106">3 つのタブのいずれかのファクトを選択して、新しいボキャブラリの定義を作成する代わりに、— たとえば、データベース列、XML ノード、または .NET クラスのメンバー: 上に、ファクトをドラッグすること、**ボキャブラリ** タブとボキャブラリの未公開バージョンにドロップします。</span><span class="sxs-lookup"><span data-stu-id="139a2-106">Alternatively, you can create a new vocabulary definition by selecting a fact from one of the three tabs—for example, a database column, an XML node, or a member of a .NET class—dragging the fact over to the **Vocabularies** tab, and dropping it to an unpublished version of a vocabulary.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="139a2-107">公開済みのボキャブラリのバージョンにはボキャブラリの定義を追加できません。</span><span class="sxs-lookup"><span data-stu-id="139a2-107">You cannot add a vocabulary definition to a vocabulary version that has been published.</span></span>  
  
### <a name="to-define-a-vocabulary-definition-as-a-constant-value"></a><span data-ttu-id="139a2-108">ボキャブラリの定義を定数値として定義するには</span><span class="sxs-lookup"><span data-stu-id="139a2-108">To define a vocabulary definition as a constant value</span></span>  
  
1.  <span data-ttu-id="139a2-109">ボキャブラリのバージョンを右クリックし、をクリックして**新しい定義の追加**です。</span><span class="sxs-lookup"><span data-stu-id="139a2-109">Right-click the vocabulary version, and then click **Add New Definition**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="139a2-110">ドラッグ アンド ファクト エクスプ ローラーの他のタブの項目をドロップすることができますも: XML スキーマ、データベースおよび .NET クラス</span><span class="sxs-lookup"><span data-stu-id="139a2-110">You can also drag and drop items from other tabs of Fact Explorer: XML Schemas, Databases and .NET Classes</span></span>  
  
2.  <span data-ttu-id="139a2-111">ボキャブラリの定義ウィザードで選択**定数値、値の範囲、または値セット**、順にクリック**次**です。</span><span class="sxs-lookup"><span data-stu-id="139a2-111">In the Vocabulary Definition Wizard, select **Constant Value, Range of Values, or Set of Values**, and then click **Next**.</span></span>  
  
3.  <span data-ttu-id="139a2-112">定義名と定義の説明を編集します。</span><span class="sxs-lookup"><span data-stu-id="139a2-112">Edit the definition name and definition description.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="139a2-113">定義の表示名の長さは最大 512 文字です。</span><span class="sxs-lookup"><span data-stu-id="139a2-113">The maximum length for a definition display name is 512 characters.</span></span>  
  
4.  <span data-ttu-id="139a2-114">選択**定数値**、順にクリック**次**です。</span><span class="sxs-lookup"><span data-stu-id="139a2-114">Select **Constant Value**, and then click **Next**.</span></span>  
  
5.  <span data-ttu-id="139a2-115">利用可能なシステム型のドロップダウン リストから、定義の種類を選択します。</span><span class="sxs-lookup"><span data-stu-id="139a2-115">Select a definition type from the drop-down list of available system types.</span></span>  
  
6.  <span data-ttu-id="139a2-116">表示名と値を編集し、クリックして**完了**です。</span><span class="sxs-lookup"><span data-stu-id="139a2-116">Edit the display name and value, and then click **Finish**.</span></span>  
  
### <a name="to-define-a-vocabulary-definition-as-a-range-of-values"></a><span data-ttu-id="139a2-117">ボキャブラリの定義を値の範囲として定義するには</span><span class="sxs-lookup"><span data-stu-id="139a2-117">To define a vocabulary definition as a range of values</span></span>  
  
1.  <span data-ttu-id="139a2-118">ボキャブラリのバージョンを右クリックし、をクリックして**新しい定義の追加**です。</span><span class="sxs-lookup"><span data-stu-id="139a2-118">Right-click the vocabulary version, and then click **Add New Definition**.</span></span>  
  
2.  <span data-ttu-id="139a2-119">ボキャブラリの定義ウィザードで選択**定数値、値の範囲、または値セット**、順にクリック**次**です。</span><span class="sxs-lookup"><span data-stu-id="139a2-119">In the Vocabulary Definition Wizard, select **Constant Value, Range of Values, or Set of Values**, and then click **Next**.</span></span>  
  
3.  <span data-ttu-id="139a2-120">定義名と定義の説明を編集します。</span><span class="sxs-lookup"><span data-stu-id="139a2-120">Edit the definition name and definition description.</span></span>  
  
4.  <span data-ttu-id="139a2-121">選択**値の範囲**、順にクリック**次**です。</span><span class="sxs-lookup"><span data-stu-id="139a2-121">Select **Range of Values**, and then click **Next**.</span></span>  
  
5.  <span data-ttu-id="139a2-122">ドロップダウン リストから定義の種類を選択します。</span><span class="sxs-lookup"><span data-stu-id="139a2-122">Select a definition type from the drop-down list.</span></span>  
  
6.  <span data-ttu-id="139a2-123">をクリックして**範囲の下限**、順にクリック**編集**範囲の下限の値を指定します。</span><span class="sxs-lookup"><span data-stu-id="139a2-123">Click **Range Low**, and then click **Edit** to specify the values for the lower range.</span></span> <span data-ttu-id="139a2-124">パラメーター定義ダイアログが表示されます。</span><span class="sxs-lookup"><span data-stu-id="139a2-124">The parameter definition dialog will be opened.</span></span>  
  
7.  <span data-ttu-id="139a2-125">選択**定数値の使用**定数の値を入力または選択**公開済みのボキャブラリから定義を使用**ボキャブラリの定義を参照し、をクリックし、 **[ok]**です。</span><span class="sxs-lookup"><span data-stu-id="139a2-125">Select **Use Constant Value** and enter a constant value, or select **Use Definition from a Published Vocabulary** and browse to a vocabulary definition, and then click **OK**.</span></span>  
  
8.  <span data-ttu-id="139a2-126">手順 6 および 7 を繰り返します**範囲の上限**です。</span><span class="sxs-lookup"><span data-stu-id="139a2-126">Repeat steps 6 and 7 for **Range High**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="139a2-127">**範囲の上限**値を超える必要があります、**範囲の下限**値。</span><span class="sxs-lookup"><span data-stu-id="139a2-127">The **Range High** value must exceed the **Range Low** value.</span></span>  
  
9. <span data-ttu-id="139a2-128">表示形式文字列を入力するか、をクリックして**既定**をクリックして既定の表示書式文字列に戻す**完了**です。</span><span class="sxs-lookup"><span data-stu-id="139a2-128">Type the display format string or click **Default** to revert to the default display format string, and then click **Finish**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="139a2-129">書式文字列は中かっこでパラメーターのインデックスを含める必要があります: たとえば、"{0}"と"{1}"—to は高値と安値の範囲のパラメーターのプレース ホルダーとして機能します。</span><span class="sxs-lookup"><span data-stu-id="139a2-129">Your format string should include parameter indexes in curly braces—for example, "{0}" and "{1}"—to serve as placeholders for the high and low range parameters.</span></span>  
  
     <span data-ttu-id="139a2-130">![ボキャブラリの定義](../core/media/3db84492-d6b8-4059-9d2c-a720ccc207b6.gif "3db84492-d6b8-4059-9d2c-a720ccc207b6")</span><span class="sxs-lookup"><span data-stu-id="139a2-130">![Vocabulary Definitions](../core/media/3db84492-d6b8-4059-9d2c-a720ccc207b6.gif "3db84492-d6b8-4059-9d2c-a720ccc207b6")</span></span>  
<span data-ttu-id="139a2-131">書式設定された文字列を含む値の範囲</span><span class="sxs-lookup"><span data-stu-id="139a2-131">Range of values with formatted string</span></span>  
  
### <a name="to-define-a-vocabulary-definition-as-a-set-of-values"></a><span data-ttu-id="139a2-132">ボキャブラリの定義を値セットとして定義するには</span><span class="sxs-lookup"><span data-stu-id="139a2-132">To define a vocabulary definition as a set of values</span></span>  
  
1.  <span data-ttu-id="139a2-133">ボキャブラリのバージョンを右クリックし、をクリックして**新しい定義の追加**です。</span><span class="sxs-lookup"><span data-stu-id="139a2-133">Right-click the vocabulary version, and then click **Add New Definition**.</span></span>  
  
2.  <span data-ttu-id="139a2-134">ボキャブラリの定義ウィザードで選択**定数値、値の範囲、または値セット**、順にクリック**次**です。</span><span class="sxs-lookup"><span data-stu-id="139a2-134">In the Vocabulary Definition Wizard, select **Constant Value, Range of Values, or Set of Values**, and then click **Next**.</span></span>  
  
3.  <span data-ttu-id="139a2-135">定義名と定義の説明を編集します。</span><span class="sxs-lookup"><span data-stu-id="139a2-135">Edit the definition name and definition description.</span></span>  
  
4.  <span data-ttu-id="139a2-136">選択**値の設定**、順にクリック**次**です。</span><span class="sxs-lookup"><span data-stu-id="139a2-136">Select **Set of Values**, and then click **Next**.</span></span>  
  
5.  <span data-ttu-id="139a2-137">定義の種類と表示名を編集します。</span><span class="sxs-lookup"><span data-stu-id="139a2-137">Enter the definition type and display name.</span></span>  
  
6.  <span data-ttu-id="139a2-138">セットにメンバーを追加するには、選択**定数値の使用**定数の値を入力または選択**公開済みのボキャブラリから定義を使用**ボキャブラリの定義を参照し、 をクリックし、**追加**です。</span><span class="sxs-lookup"><span data-stu-id="139a2-138">To add a member to the set, select **Use Constant Value** and enter a constant value, or select **Use Definition from a Published Vocabulary** and browse to a vocabulary definition, and then click **Add**.</span></span>  
  
7.  <span data-ttu-id="139a2-139">追加するアイテム数の分だけ、定数やボキャブラリの定義の組み合わせを使用して、手順 6. を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="139a2-139">Repeat step 6, with any combination of constants or vocabulary definitions, for as many items as you want to include in your set.</span></span>  
  
8.  <span data-ttu-id="139a2-140">セットの相対順序内のメンバーを移動するには、選択してをクリックして**を**または**ダウン**です。</span><span class="sxs-lookup"><span data-stu-id="139a2-140">To move a member within the relative order of the set, select it and then click **Up** or **Down**.</span></span>  
  
9. <span data-ttu-id="139a2-141">セットからメンバーを削除するには、選択してをクリックして**削除**です。</span><span class="sxs-lookup"><span data-stu-id="139a2-141">To remove a member from the set, select it and then click **Remove**.</span></span>  
  
10. <span data-ttu-id="139a2-142">セットが完了したら、をクリックして**完了**です。</span><span class="sxs-lookup"><span data-stu-id="139a2-142">When you have completed your set, click **Finish**.</span></span>  
  
     <span data-ttu-id="139a2-143">![ボキャブラリの定義](../core/media/461d0d70-52ed-4f43-927d-3efb1fbfb934.gif "461d0d70-52ed-4f43-927d-3efb1fbfb934")</span><span class="sxs-lookup"><span data-stu-id="139a2-143">![Vocabulary Definitions](../core/media/461d0d70-52ed-4f43-927d-3efb1fbfb934.gif "461d0d70-52ed-4f43-927d-3efb1fbfb934")</span></span>  
<span data-ttu-id="139a2-144">[値セット]</span><span class="sxs-lookup"><span data-stu-id="139a2-144">Set of values</span></span>  
  
### <a name="to-define-a-vocabulary-definition-as-a-net-class-or-class-member"></a><span data-ttu-id="139a2-145">ボキャブラリの定義を .NET クラスまたはクラス メンバーとして定義するには</span><span class="sxs-lookup"><span data-stu-id="139a2-145">To define a vocabulary definition as a .NET class or class member</span></span>  
  
1.  <span data-ttu-id="139a2-146">ボキャブラリのバージョンを右クリックし、をクリックして**新しい定義の追加**です。</span><span class="sxs-lookup"><span data-stu-id="139a2-146">Right-click the vocabulary version, and then click **Add New Definition**.</span></span>  
  
2.  <span data-ttu-id="139a2-147">ボキャブラリの定義ウィザードで選択**.NET クラスまたはクラス メンバー**、クリックして**次**です。</span><span class="sxs-lookup"><span data-stu-id="139a2-147">In the Vocabulary Definition Wizard, select **.NET Class or Class Member**, and then click **Next**.</span></span>  
  
3.  <span data-ttu-id="139a2-148">編集、**定義名**と**説明**フィールドです。</span><span class="sxs-lookup"><span data-stu-id="139a2-148">Edit the **Definition Name** and **Description** fields.</span></span>  
  
4.  <span data-ttu-id="139a2-149">**[参照]**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="139a2-149">Click **Browse**.</span></span>  
  
5.  <span data-ttu-id="139a2-150">**.NET アセンブリ**ダイアログ ボックスでは、アセンブリを選択し、をクリックして**OK**です。</span><span class="sxs-lookup"><span data-stu-id="139a2-150">In the **.NET Assemblies** dialog box, select an assembly, and then click **OK**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="139a2-151">アセンブリは、グローバル アセンブリ キャッシュ (GAC) 内に格納されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="139a2-151">The assemblies have to be in the global assembly cache (GAC).</span></span> <span data-ttu-id="139a2-152">ビジネス ルール作成ツールは、.NET アセンブリで参照するときに .NET アセンブリを読み込みます、**ファクト エクスプ ローラー**ウィンドウまたは、 **.NET クラスまたはクラス メンバーの定義**のページ、**ボキャブラリ定義**ウィンドウです。</span><span class="sxs-lookup"><span data-stu-id="139a2-152">The business rule composer loads a .NET assembly when you browse for the .NET assembly in the **Facts Explorer** window or in the **.NET Class or Class Member Definition** page of the **Vocabulary Definition** window.</span></span>  <span data-ttu-id="139a2-153">GAC でアセンブリを更新した場合は、ビジネス ルール作成ツールを終了してから再起動し、更新した .NET アセンブリを読み込みます。</span><span class="sxs-lookup"><span data-stu-id="139a2-153">If you update the assembly in the GAC, close the business rule composer and restart it to load the updated .NET assembly.</span></span> <span data-ttu-id="139a2-154">ビジネス ルール作成ツールでは、アセンブリが自動更新されません。</span><span class="sxs-lookup"><span data-stu-id="139a2-154">The business rule composer does not refresh the assembly automatically.</span></span>  
  
6.  <span data-ttu-id="139a2-155">アセンブリ ノードを展開します。</span><span class="sxs-lookup"><span data-stu-id="139a2-155">Expand the assembly node.</span></span>  
  
7.  <span data-ttu-id="139a2-156">クラス、またはクラスを展開およびクラスのメンバーを選択し、をクリックして**OK**です。</span><span class="sxs-lookup"><span data-stu-id="139a2-156">Select a class, or expand a class and select a class member, and then click **OK**.</span></span>  
  
8.  <span data-ttu-id="139a2-157">をクリックして**次**、し、表示名を指定します。</span><span class="sxs-lookup"><span data-stu-id="139a2-157">Click **Next**, and specify the display name.</span></span>  
  
     <span data-ttu-id="139a2-158">詳細については、このトピックの後半にある「パラメーターを使用して、ボキャブラリの定義の表示書式を指定するには」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="139a2-158">For more information, see "To specify the display format of a vocabulary definition by using parameters" later in this topic.</span></span>  
  
9. <span data-ttu-id="139a2-159">**[完了]**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="139a2-159">Click **Finish**.</span></span>  
  
     <span data-ttu-id="139a2-160">![ボキャブラリの定義](../core/media/4259101f-26dd-488f-81c0-f8d225e4016e.gif "4259101f-26dd-488f-81c0-f8d225e4016e")</span><span class="sxs-lookup"><span data-stu-id="139a2-160">![Vocabulary Definitions](../core/media/4259101f-26dd-488f-81c0-f8d225e4016e.gif "4259101f-26dd-488f-81c0-f8d225e4016e")</span></span>  
<span data-ttu-id="139a2-161">Net オブジェクトのボキャブラリの定義</span><span class="sxs-lookup"><span data-stu-id="139a2-161">Net object vocabulary definition</span></span>  
  
### <a name="to-define-a-vocabulary-definition-as-an-xml-document-element-or-attribute"></a><span data-ttu-id="139a2-162">XML ドキュメントの要素または属性としてボキャブラリの定義を定義するには</span><span class="sxs-lookup"><span data-stu-id="139a2-162">To define a vocabulary definition as an XML document element or attribute</span></span>  
  
1.  <span data-ttu-id="139a2-163">ボキャブラリのバージョンを右クリックし、をクリックして**新しい定義の追加**です。</span><span class="sxs-lookup"><span data-stu-id="139a2-163">Right-click the vocabulary version, and then click **Add New Definition**.</span></span>  
  
2.  <span data-ttu-id="139a2-164">ボキャブラリの定義ウィザードで選択**XML ドキュメントの要素または属性**、クリックして**次**です。</span><span class="sxs-lookup"><span data-stu-id="139a2-164">In the Vocabulary Definition Wizard, select **XML Document Element or Attribute**, and then click **Next**.</span></span>  
  
3.  <span data-ttu-id="139a2-165">定義名と定義の説明を入力します。</span><span class="sxs-lookup"><span data-stu-id="139a2-165">Type a definition name and a definition description.</span></span>  
  
4.  <span data-ttu-id="139a2-166">をクリックして**参照**をスキーマ ファイルを検索およびドキュメントの要素または属性を指定します。</span><span class="sxs-lookup"><span data-stu-id="139a2-166">Click **Browse** to locate a schema file and specify a document element or attribute.</span></span>  
  
5.  <span data-ttu-id="139a2-167">ドロップダウン リストから、スキーマ内の要素または属性の型と互換性のある型を選択します。</span><span class="sxs-lookup"><span data-stu-id="139a2-167">From the drop-down list, select a type that is compatible with the type of the element or attribute in the schema.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="139a2-168">特定の型への有効なキャスト、または特定の型からドキュメントの要素または属性の型への有効なキャストを行うことができなかった場合、実行時にエラーが生成されます。</span><span class="sxs-lookup"><span data-stu-id="139a2-168">If a valid cast cannot be done to or from the specified type to the type of the document element or attribute, you will get an error at run time.</span></span>  
  
6.  <span data-ttu-id="139a2-169">要素または属性の値を取得するかどうかを示すために、またはその値を設定するために、操作の種類を選択します。</span><span class="sxs-lookup"><span data-stu-id="139a2-169">Select an operation type to indicate whether you plan to get the value of the element or attribute, or to set its value.</span></span>  
  
7.  <span data-ttu-id="139a2-170">値を設定する場合は、クリックして**次**、し、表示形式を指定します。</span><span class="sxs-lookup"><span data-stu-id="139a2-170">If you chose to set the value, click **Next**, and then specify the display format.</span></span>  
  
8.  <span data-ttu-id="139a2-171">**[完了]**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="139a2-171">Click **Finish**.</span></span>  
  
     <span data-ttu-id="139a2-172">![ボキャブラリの定義](../core/media/fd81b534-ec41-4147-b716-1e10ffc01d6f.gif "fd81b534-ec41-4147-b716-1e10ffc01d6f")</span><span class="sxs-lookup"><span data-stu-id="139a2-172">![Vocabulary Definitions](../core/media/fd81b534-ec41-4147-b716-1e10ffc01d6f.gif "fd81b534-ec41-4147-b716-1e10ffc01d6f")</span></span>  
<span data-ttu-id="139a2-173">XML のボキャブラリの定義</span><span class="sxs-lookup"><span data-stu-id="139a2-173">XML vocabulary definition</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="139a2-174">定義済み要素およびドキュメント型があるかどうかは検証されません。</span><span class="sxs-lookup"><span data-stu-id="139a2-174">The existence of the defined element and the document type is never validated.</span></span> <span data-ttu-id="139a2-175">アサート済みドキュメントが要素を持っていない場合は、実行時エラーが生成されます。</span><span class="sxs-lookup"><span data-stu-id="139a2-175">If the asserted document does not have the element, you will get a runtime error.</span></span> <span data-ttu-id="139a2-176">不明なドキュメントの種類にドキュメントをアサートする場合は単に無視されます。</span><span class="sxs-lookup"><span data-stu-id="139a2-176">If you assert a document with unknown document type, it will simply be ignored.</span></span>  
  
#### <a name="to-define-a-vocabulary-definition-as-a-database-table-or-database-table-column"></a><span data-ttu-id="139a2-177">ボキャブラリの定義をデータベース テーブルまたはデータベース テーブル列として定義するには</span><span class="sxs-lookup"><span data-stu-id="139a2-177">To define a vocabulary definition as a database table or database table column</span></span>  
  
1.  <span data-ttu-id="139a2-178">ボキャブラリのバージョンを右クリックし、をクリックして**新しい定義の追加**です。</span><span class="sxs-lookup"><span data-stu-id="139a2-178">Right-click the vocabulary version and then click **Add New Definition**.</span></span>  
  
2.  <span data-ttu-id="139a2-179">ボキャブラリの定義ウィザードで選択**データベース テーブルまたはデータベース テーブル列の定義**、順にクリック**次**です。</span><span class="sxs-lookup"><span data-stu-id="139a2-179">In the Vocabulary Definition Wizard, select **Database Table or Database Table Column Definition**, and then click **Next**.</span></span>  
  
3.  <span data-ttu-id="139a2-180">定義名と定義の説明を入力します。</span><span class="sxs-lookup"><span data-stu-id="139a2-180">Type a definition name and definition description.</span></span>  
  
4.  <span data-ttu-id="139a2-181">**[参照]**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="139a2-181">Click **Browse**.</span></span>  
  
5.  <span data-ttu-id="139a2-182">接続する SQL Server コンピューターを選択します。</span><span class="sxs-lookup"><span data-stu-id="139a2-182">Select a SQL Server computer to connect with.</span></span> <span data-ttu-id="139a2-183">SQL Server コンピューターが現在開始されていない場合は、選択、**停止されている場合、SQL Server 開始**チェック ボックスをオンします。</span><span class="sxs-lookup"><span data-stu-id="139a2-183">If the SQL Server computer is not currently started, select the **Start SQL Server if it is stopped** check box.</span></span>  
  
6.  <span data-ttu-id="139a2-184">認証の種類を選択します。</span><span class="sxs-lookup"><span data-stu-id="139a2-184">Select an authentication type.</span></span> <span data-ttu-id="139a2-185">SQL Server 認証を選択した場合のログオン名とパスワードを入力し、をクリックして**OK**です。</span><span class="sxs-lookup"><span data-stu-id="139a2-185">If you select SQL Server authentication, type your logon name and password, and then click **OK**.</span></span>  
  
7.  <span data-ttu-id="139a2-186">テーブルまたはテーブルの列にバインドし、そのをクリックする選択**OK**です。</span><span class="sxs-lookup"><span data-stu-id="139a2-186">Select the table or table column that you want to bind to, and then click **OK**.</span></span>  
  
8.  <span data-ttu-id="139a2-187">テーブル列を選択した場合は、値を取得するか、または値を設定するかを選択します。</span><span class="sxs-lookup"><span data-stu-id="139a2-187">If you selected a table column, select whether you want to get its value or set its value.</span></span> <span data-ttu-id="139a2-188">値の取得を選択した場合は、表示書式を入力します。</span><span class="sxs-lookup"><span data-stu-id="139a2-188">If you choose to get its value, type the display name.</span></span> <span data-ttu-id="139a2-189">その値を設定する場合をクリックして**次**表示形式を指定します。</span><span class="sxs-lookup"><span data-stu-id="139a2-189">If you choose to set its value, click **Next** to specify the display format.</span></span>  
  
     <span data-ttu-id="139a2-190">詳細については、このトピックの後半にある「パラメーターを使用して、ボキャブラリの定義の表示書式を指定するには」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="139a2-190">For more information, see "To specify the display format of a vocabulary definition by using parameters" later in this topic.</span></span>  
  
9. <span data-ttu-id="139a2-191">テーブルを選択した場合は、表示名を入力します。</span><span class="sxs-lookup"><span data-stu-id="139a2-191">If you selected a table, type a display name.</span></span>  
  
10. <span data-ttu-id="139a2-192">**[完了]**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="139a2-192">Click **Finish**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="139a2-193">既定では、 **DataConnection**バインディングの使用</span><span class="sxs-lookup"><span data-stu-id="139a2-193">By default, **DataConnection** binding is used</span></span>  
  
     <span data-ttu-id="139a2-194">![ボキャブラリの定義](../core/media/f8121306-cd73-4997-adc4-71a055dfd824.gif "f8121306-cd73-4997-adc4-71a055dfd824")</span><span class="sxs-lookup"><span data-stu-id="139a2-194">![Vocabulary Definitions](../core/media/f8121306-cd73-4997-adc4-71a055dfd824.gif "f8121306-cd73-4997-adc4-71a055dfd824")</span></span>  
<span data-ttu-id="139a2-195">データベースのボキャブラリの定義</span><span class="sxs-lookup"><span data-stu-id="139a2-195">Database vocabulary definition</span></span>  
  
#### <a name="to-specify-the-display-format-of-a-vocabulary-definition-by-using-parameters"></a><span data-ttu-id="139a2-196">パラメーターを使用して、ボキャブラリの定義の表示書式を指定するには</span><span class="sxs-lookup"><span data-stu-id="139a2-196">To specify the display format of a vocabulary definition by using parameters</span></span>  
  
1.  <span data-ttu-id="139a2-197">一覧からパラメーターを選択**パラメーター**をクリックしてボキャブラリの定義ウィザードでは、**編集**です。</span><span class="sxs-lookup"><span data-stu-id="139a2-197">Select a parameter from the list of **Parameters** in Vocabulary Definition Wizard, and then click **Edit**.</span></span>  
  
2.  <span data-ttu-id="139a2-198">選択**定数値の使用**定数の値を入力または選択**公開済みのボキャブラリから定義を使用**ボキャブラリの定義を参照し、をクリックし、 **[ok]**です。</span><span class="sxs-lookup"><span data-stu-id="139a2-198">Select **Use Constant Value** and enter a constant value, or select **Use Definition from a Published Vocabulary** and browse to a vocabulary definition, and then click **OK**.</span></span>  
  
3.  <span data-ttu-id="139a2-199">表示形式文字列を入力するか、をクリックして**既定**をクリックして既定の表示書式文字列に戻す**完了**です。</span><span class="sxs-lookup"><span data-stu-id="139a2-199">Type the display format string or click **Default** to revert to the default display format string, and then click **Finish**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="139a2-200">書式文字列は中かっこでパラメーターのインデックスを含める必要があります: たとえば、"{0}"と"{1}"—to は、パラメーターのプレース ホルダーとして機能します。</span><span class="sxs-lookup"><span data-stu-id="139a2-200">Your format string should include parameter indexes in curly braces—for example, "{0}" and "{1}"—to serve as placeholders for the parameters.</span></span>  
  
     <span data-ttu-id="139a2-201">![ボキャブラリの定義](../core/media/822f78f4-278a-4211-83ad-44032fa81f13.gif "822f78f4-278a-4211-83ad-44032fa81f13")</span><span class="sxs-lookup"><span data-stu-id="139a2-201">![Vocabulary Definitions](../core/media/822f78f4-278a-4211-83ad-44032fa81f13.gif "822f78f4-278a-4211-83ad-44032fa81f13")</span></span>  
<span data-ttu-id="139a2-202">パラメーターによるボキャブラリの定義</span><span class="sxs-lookup"><span data-stu-id="139a2-202">Vocabulary definition with parameters</span></span>