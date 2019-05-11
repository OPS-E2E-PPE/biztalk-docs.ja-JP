---
title: ボキャブラリの定義を作成する方法 |Microsoft Docs
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
- vocabularies, definitions
ms.assetid: 6f8fc4c2-2c46-4a7d-a02f-89de0396e3e2
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 43049d66562cb011e5d1d4698cbab9cef7bc6860
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65385397"
---
# <a name="how-to-create-vocabulary-definitions"></a><span data-ttu-id="edaee-102">ボキャブラリの定義を作成する方法</span><span class="sxs-lookup"><span data-stu-id="edaee-102">How to Create Vocabulary Definitions</span></span>
<span data-ttu-id="edaee-103">ボキャブラリの定義ウィザードを使用して、ボキャブラリの定義を作成することができます。</span><span class="sxs-lookup"><span data-stu-id="edaee-103">You can use the Vocabulary Definition Wizard to create vocabulary definitions.</span></span> <span data-ttu-id="edaee-104">ボキャブラリの定義は、定数値、値の範囲、一連の値、または .NET アセンブリ、XML ドキュメント、またはデータベース テーブルの要素として定義できます。</span><span class="sxs-lookup"><span data-stu-id="edaee-104">You can define a vocabulary definition as a constant value, a range of values, a set of values, or elements of a .NET assembly, XML document, or database table.</span></span> <span data-ttu-id="edaee-105">パブリック変数を選択する場合があります**取得**と**設定**データベースや XML の定義ウィザードのオプションと同様です。</span><span class="sxs-lookup"><span data-stu-id="edaee-105">If you select a public variable, there will be **Get** and **Set** options just like in Database and XML definition wizard.</span></span>  
  
 <span data-ttu-id="edaee-106">3 つのタブのいずれかからファクトを選択して、新しいボキャブラリの定義を作成する代わりに、— データベース列、XML ノード、または .NET クラスのメンバー-という事実を上にドラッグする、**ボキャブラリ** タブとボキャブラリの未公開バージョンにドロップします。</span><span class="sxs-lookup"><span data-stu-id="edaee-106">Alternatively, you can create a new vocabulary definition by selecting a fact from one of the three tabs—for example, a database column, an XML node, or a member of a .NET class—dragging the fact over to the **Vocabularies** tab, and dropping it to an unpublished version of a vocabulary.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="edaee-107">パブリッシュされたボキャブラリのバージョンには、ボキャブラリの定義を追加できません。</span><span class="sxs-lookup"><span data-stu-id="edaee-107">You cannot add a vocabulary definition to a vocabulary version that has been published.</span></span>  
  
### <a name="to-define-a-vocabulary-definition-as-a-constant-value"></a><span data-ttu-id="edaee-108">定数値としてボキャブラリの定義を定義するには</span><span class="sxs-lookup"><span data-stu-id="edaee-108">To define a vocabulary definition as a constant value</span></span>  
  
1.  <span data-ttu-id="edaee-109">ボキャブラリのバージョンを右クリックし、をクリックし、**新しい定義の追加**します。</span><span class="sxs-lookup"><span data-stu-id="edaee-109">Right-click the vocabulary version, and then click **Add New Definition**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="edaee-110">ドラッグし、ファクト エクスプ ローラーの他のタブから項目をドロップすることができますもします。XML スキーマ、データベースおよび .NET クラス</span><span class="sxs-lookup"><span data-stu-id="edaee-110">You can also drag and drop items from other tabs of Fact Explorer: XML Schemas, Databases and .NET Classes</span></span>  
  
2.  <span data-ttu-id="edaee-111">ボキャブラリの定義ウィザードで選択**定数値、値の範囲、または値セット**、順にクリックします**次**します。</span><span class="sxs-lookup"><span data-stu-id="edaee-111">In the Vocabulary Definition Wizard, select **Constant Value, Range of Values, or Set of Values**, and then click **Next**.</span></span>  
  
3.  <span data-ttu-id="edaee-112">定義の名前と定義の説明を編集します。</span><span class="sxs-lookup"><span data-stu-id="edaee-112">Edit the definition name and definition description.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="edaee-113">定義の表示名の最大長は、512 文字です。</span><span class="sxs-lookup"><span data-stu-id="edaee-113">The maximum length for a definition display name is 512 characters.</span></span>  
  
4.  <span data-ttu-id="edaee-114">選択**定数値**、 をクリックし、**次**。</span><span class="sxs-lookup"><span data-stu-id="edaee-114">Select **Constant Value**, and then click **Next**.</span></span>  
  
5.  <span data-ttu-id="edaee-115">使用可能なシステムの種類のドロップダウン リストから定義の種類を選択します。</span><span class="sxs-lookup"><span data-stu-id="edaee-115">Select a definition type from the drop-down list of available system types.</span></span>  
  
6.  <span data-ttu-id="edaee-116">表示名と値を編集し、クリックして**完了**します。</span><span class="sxs-lookup"><span data-stu-id="edaee-116">Edit the display name and value, and then click **Finish**.</span></span>  
  
### <a name="to-define-a-vocabulary-definition-as-a-range-of-values"></a><span data-ttu-id="edaee-117">値の範囲のとしてボキャブラリの定義を定義するには</span><span class="sxs-lookup"><span data-stu-id="edaee-117">To define a vocabulary definition as a range of values</span></span>  
  
1.  <span data-ttu-id="edaee-118">ボキャブラリのバージョンを右クリックし、をクリックし、**新しい定義の追加**します。</span><span class="sxs-lookup"><span data-stu-id="edaee-118">Right-click the vocabulary version, and then click **Add New Definition**.</span></span>  
  
2.  <span data-ttu-id="edaee-119">ボキャブラリの定義ウィザードで選択**定数値、値の範囲、または値セット**、順にクリックします**次**します。</span><span class="sxs-lookup"><span data-stu-id="edaee-119">In the Vocabulary Definition Wizard, select **Constant Value, Range of Values, or Set of Values**, and then click **Next**.</span></span>  
  
3.  <span data-ttu-id="edaee-120">定義の名前と定義の説明を編集します。</span><span class="sxs-lookup"><span data-stu-id="edaee-120">Edit the definition name and definition description.</span></span>  
  
4.  <span data-ttu-id="edaee-121">選択**値の範囲**、 をクリックし、**次**。</span><span class="sxs-lookup"><span data-stu-id="edaee-121">Select **Range of Values**, and then click **Next**.</span></span>  
  
5.  <span data-ttu-id="edaee-122">ドロップダウン リストから定義の種類を選択します。</span><span class="sxs-lookup"><span data-stu-id="edaee-122">Select a definition type from the drop-down list.</span></span>  
  
6.  <span data-ttu-id="edaee-123">クリックして**範囲の下限**、順にクリックします**編集**範囲の下限の値を指定します。</span><span class="sxs-lookup"><span data-stu-id="edaee-123">Click **Range Low**, and then click **Edit** to specify the values for the lower range.</span></span> <span data-ttu-id="edaee-124">パラメーターの定義 ダイアログ ボックスが開きます。</span><span class="sxs-lookup"><span data-stu-id="edaee-124">The parameter definition dialog will be opened.</span></span>  
  
7.  <span data-ttu-id="edaee-125">選択**定数の値を使用**定数の値を入力または選択**公開済みのボキャブラリから定義を使用**ボキャブラリの定義を参照し をクリックし、 **ok**。</span><span class="sxs-lookup"><span data-stu-id="edaee-125">Select **Use Constant Value** and enter a constant value, or select **Use Definition from a Published Vocabulary** and browse to a vocabulary definition, and then click **OK**.</span></span>  
  
8.  <span data-ttu-id="edaee-126">手順 6 と 7 を**範囲の上限**します。</span><span class="sxs-lookup"><span data-stu-id="edaee-126">Repeat steps 6 and 7 for **Range High**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="edaee-127">**範囲の上限**値を超えることは、**範囲の下限**値。</span><span class="sxs-lookup"><span data-stu-id="edaee-127">The **Range High** value must exceed the **Range Low** value.</span></span>  
  
9. <span data-ttu-id="edaee-128">表示書式文字列を入力するかクリックして**既定**をクリックして既定の表示書式文字列に戻す**完了**します。</span><span class="sxs-lookup"><span data-stu-id="edaee-128">Type the display format string or click **Default** to revert to the default display format string, and then click **Finish**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="edaee-129">書式指定文字列は中かっこでパラメーターのインデックスを含める必要があります: たとえば、"{0}「と」{1}"-高値と安値の範囲のパラメーターのプレース ホルダーとして機能します。</span><span class="sxs-lookup"><span data-stu-id="edaee-129">Your format string should include parameter indexes in curly braces—for example, "{0}" and "{1}"—to serve as placeholders for the high and low range parameters.</span></span>  
  
     <span data-ttu-id="edaee-130">![ボキャブラリの定義](../core/media/3db84492-d6b8-4059-9d2c-a720ccc207b6.gif "3db84492-d6b8-4059-9d2c-a720ccc207b6")</span><span class="sxs-lookup"><span data-stu-id="edaee-130">![Vocabulary Definitions](../core/media/3db84492-d6b8-4059-9d2c-a720ccc207b6.gif "3db84492-d6b8-4059-9d2c-a720ccc207b6")</span></span>  
<span data-ttu-id="edaee-131">書式設定された文字列の値の範囲</span><span class="sxs-lookup"><span data-stu-id="edaee-131">Range of values with formatted string</span></span>  
  
### <a name="to-define-a-vocabulary-definition-as-a-set-of-values"></a><span data-ttu-id="edaee-132">一連の値としてボキャブラリの定義を定義するには</span><span class="sxs-lookup"><span data-stu-id="edaee-132">To define a vocabulary definition as a set of values</span></span>  
  
1.  <span data-ttu-id="edaee-133">ボキャブラリのバージョンを右クリックし、をクリックし、**新しい定義の追加**します。</span><span class="sxs-lookup"><span data-stu-id="edaee-133">Right-click the vocabulary version, and then click **Add New Definition**.</span></span>  
  
2.  <span data-ttu-id="edaee-134">ボキャブラリの定義ウィザードで選択**定数値、値の範囲、または値セット**、順にクリックします**次**します。</span><span class="sxs-lookup"><span data-stu-id="edaee-134">In the Vocabulary Definition Wizard, select **Constant Value, Range of Values, or Set of Values**, and then click **Next**.</span></span>  
  
3.  <span data-ttu-id="edaee-135">定義の名前と定義の説明を編集します。</span><span class="sxs-lookup"><span data-stu-id="edaee-135">Edit the definition name and definition description.</span></span>  
  
4.  <span data-ttu-id="edaee-136">選択**値セットの**、順にクリックします**次**します。</span><span class="sxs-lookup"><span data-stu-id="edaee-136">Select **Set of Values**, and then click **Next**.</span></span>  
  
5.  <span data-ttu-id="edaee-137">定義の種類を入力し、名前を表示します。</span><span class="sxs-lookup"><span data-stu-id="edaee-137">Enter the definition type and display name.</span></span>  
  
6.  <span data-ttu-id="edaee-138">セットにメンバーを追加するには、選択**定数値の使用**定数の値を入力または選択**公開済みのボキャブラリから定義を使用**ボキャブラリの定義を参照し、 をクリックし、**追加**します。</span><span class="sxs-lookup"><span data-stu-id="edaee-138">To add a member to the set, select **Use Constant Value** and enter a constant value, or select **Use Definition from a Published Vocabulary** and browse to a vocabulary definition, and then click **Add**.</span></span>  
  
7.  <span data-ttu-id="edaee-139">手順 6、定数やボキャブラリの定義の任意の組み合わせをセットに含める項目の数を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="edaee-139">Repeat step 6, with any combination of constants or vocabulary definitions, for as many items as you want to include in your set.</span></span>  
  
8.  <span data-ttu-id="edaee-140">セットの相対順序内のメンバーを移動するに選択してクリックして**を**または**ダウン**します。</span><span class="sxs-lookup"><span data-stu-id="edaee-140">To move a member within the relative order of the set, select it and then click **Up** or **Down**.</span></span>  
  
9. <span data-ttu-id="edaee-141">セットからメンバーを削除する選択してクリックして**削除**します。</span><span class="sxs-lookup"><span data-stu-id="edaee-141">To remove a member from the set, select it and then click **Remove**.</span></span>  
  
10. <span data-ttu-id="edaee-142">セットが完了したら、クリックして**完了**します。</span><span class="sxs-lookup"><span data-stu-id="edaee-142">When you have completed your set, click **Finish**.</span></span>  
  
     <span data-ttu-id="edaee-143">![ボキャブラリの定義](../core/media/461d0d70-52ed-4f43-927d-3efb1fbfb934.gif "461d0d70-52ed-4f43-927d-3efb1fbfb934")</span><span class="sxs-lookup"><span data-stu-id="edaee-143">![Vocabulary Definitions](../core/media/461d0d70-52ed-4f43-927d-3efb1fbfb934.gif "461d0d70-52ed-4f43-927d-3efb1fbfb934")</span></span>  
<span data-ttu-id="edaee-144">値のセット</span><span class="sxs-lookup"><span data-stu-id="edaee-144">Set of values</span></span>  
  
### <a name="to-define-a-vocabulary-definition-as-a-net-class-or-class-member"></a><span data-ttu-id="edaee-145">.NET クラスまたはクラス メンバーとしてボキャブラリの定義を定義するには</span><span class="sxs-lookup"><span data-stu-id="edaee-145">To define a vocabulary definition as a .NET class or class member</span></span>  
  
1.  <span data-ttu-id="edaee-146">ボキャブラリのバージョンを右クリックし、をクリックし、**新しい定義の追加**します。</span><span class="sxs-lookup"><span data-stu-id="edaee-146">Right-click the vocabulary version, and then click **Add New Definition**.</span></span>  
  
2.  <span data-ttu-id="edaee-147">ボキャブラリの定義ウィザードで選択 **.NET クラスまたはクラス メンバー**、 をクリックし、**次**。</span><span class="sxs-lookup"><span data-stu-id="edaee-147">In the Vocabulary Definition Wizard, select **.NET Class or Class Member**, and then click **Next**.</span></span>  
  
3.  <span data-ttu-id="edaee-148">編集、**定義名**と**説明**フィールド。</span><span class="sxs-lookup"><span data-stu-id="edaee-148">Edit the **Definition Name** and **Description** fields.</span></span>  
  
4.  <span data-ttu-id="edaee-149">**[参照]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="edaee-149">Click **Browse**.</span></span>  
  
5.  <span data-ttu-id="edaee-150">**.NET アセンブリ** ダイアログ ボックスでは、アセンブリを選択し、クリックして**OK**します。</span><span class="sxs-lookup"><span data-stu-id="edaee-150">In the **.NET Assemblies** dialog box, select an assembly, and then click **OK**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="edaee-151">アセンブリは、グローバル アセンブリ キャッシュ (GAC) 内に格納されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="edaee-151">The assemblies have to be in the global assembly cache (GAC).</span></span> <span data-ttu-id="edaee-152">ビジネス ルール作成ツールは、.NET アセンブリで参照するときに .NET アセンブリを読み込みます、**ファクト エクスプ ローラー**ウィンドウまたは、 **.NET クラスまたはクラス メンバーの定義**のページ、**ボキャブラリ定義**ウィンドウです。</span><span class="sxs-lookup"><span data-stu-id="edaee-152">The business rule composer loads a .NET assembly when you browse for the .NET assembly in the **Facts Explorer** window or in the **.NET Class or Class Member Definition** page of the **Vocabulary Definition** window.</span></span>  <span data-ttu-id="edaee-153">GAC でアセンブリを更新した場合は、ビジネス ルール作成ツールを終了してから再起動し、更新した .NET アセンブリを読み込みます。</span><span class="sxs-lookup"><span data-stu-id="edaee-153">If you update the assembly in the GAC, close the business rule composer and restart it to load the updated .NET assembly.</span></span> <span data-ttu-id="edaee-154">ビジネス ルール作成ツールでは、アセンブリが自動更新されません。</span><span class="sxs-lookup"><span data-stu-id="edaee-154">The business rule composer does not refresh the assembly automatically.</span></span>  
  
6.  <span data-ttu-id="edaee-155">アセンブリ ノードを展開します。</span><span class="sxs-lookup"><span data-stu-id="edaee-155">Expand the assembly node.</span></span>  
  
7.  <span data-ttu-id="edaee-156">クラスを選択またはクラスを展開し、クラスのメンバーを選択し、順にクリックします**OK**します。</span><span class="sxs-lookup"><span data-stu-id="edaee-156">Select a class, or expand a class and select a class member, and then click **OK**.</span></span>  
  
8.  <span data-ttu-id="edaee-157">をクリックして**次**、し、表示名を指定します。</span><span class="sxs-lookup"><span data-stu-id="edaee-157">Click **Next**, and specify the display name.</span></span>  
  
     <span data-ttu-id="edaee-158">詳細については、このトピックの"パラメーターを使用して、ボキャブラリの定義の表示形式を指定する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="edaee-158">For more information, see "To specify the display format of a vocabulary definition by using parameters" later in this topic.</span></span>  
  
9. <span data-ttu-id="edaee-159">**[完了]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="edaee-159">Click **Finish**.</span></span>  
  
     <span data-ttu-id="edaee-160">![ボキャブラリの定義](../core/media/4259101f-26dd-488f-81c0-f8d225e4016e.gif "4259101f-26dd-488f-81c0-f8d225e4016e")</span><span class="sxs-lookup"><span data-stu-id="edaee-160">![Vocabulary Definitions](../core/media/4259101f-26dd-488f-81c0-f8d225e4016e.gif "4259101f-26dd-488f-81c0-f8d225e4016e")</span></span>  
<span data-ttu-id="edaee-161">Net オブジェクトのボキャブラリの定義</span><span class="sxs-lookup"><span data-stu-id="edaee-161">Net object vocabulary definition</span></span>  
  
### <a name="to-define-a-vocabulary-definition-as-an-xml-document-element-or-attribute"></a><span data-ttu-id="edaee-162">XML ドキュメントの要素または属性としてボキャブラリの定義を定義するには</span><span class="sxs-lookup"><span data-stu-id="edaee-162">To define a vocabulary definition as an XML document element or attribute</span></span>  
  
1.  <span data-ttu-id="edaee-163">ボキャブラリのバージョンを右クリックし、をクリックし、**新しい定義の追加**します。</span><span class="sxs-lookup"><span data-stu-id="edaee-163">Right-click the vocabulary version, and then click **Add New Definition**.</span></span>  
  
2.  <span data-ttu-id="edaee-164">ボキャブラリの定義ウィザードで選択**XML ドキュメントの要素または属性**、 をクリックし、**次**。</span><span class="sxs-lookup"><span data-stu-id="edaee-164">In the Vocabulary Definition Wizard, select **XML Document Element or Attribute**, and then click **Next**.</span></span>  
  
3.  <span data-ttu-id="edaee-165">定義名と定義の説明を入力します。</span><span class="sxs-lookup"><span data-stu-id="edaee-165">Type a definition name and a definition description.</span></span>  
  
4.  <span data-ttu-id="edaee-166">クリックして**参照**をスキーマ ファイルを検索およびドキュメントの要素または属性を指定します。</span><span class="sxs-lookup"><span data-stu-id="edaee-166">Click **Browse** to locate a schema file and specify a document element or attribute.</span></span>  
  
5.  <span data-ttu-id="edaee-167">ドロップダウン リストから要素またはスキーマ内の属性の型と互換性がある型を選択します。</span><span class="sxs-lookup"><span data-stu-id="edaee-167">From the drop-down list, select a type that is compatible with the type of the element or attribute in the schema.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="edaee-168">有効なキャストできない場合、またはドキュメントの要素または属性の型に指定した型から、実行時にエラーが表示されます。</span><span class="sxs-lookup"><span data-stu-id="edaee-168">If a valid cast cannot be done to or from the specified type to the type of the document element or attribute, you will get an error at run time.</span></span>  
  
6.  <span data-ttu-id="edaee-169">要素または属性の値を取得する、またはその値を設定するかどうかを示す操作の種類を選択します。</span><span class="sxs-lookup"><span data-stu-id="edaee-169">Select an operation type to indicate whether you plan to get the value of the element or attribute, or to set its value.</span></span>  
  
7.  <span data-ttu-id="edaee-170">値を設定する場合は、クリックして**次**、し、表示形式を指定します。</span><span class="sxs-lookup"><span data-stu-id="edaee-170">If you chose to set the value, click **Next**, and then specify the display format.</span></span>  
  
8.  <span data-ttu-id="edaee-171">**[完了]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="edaee-171">Click **Finish**.</span></span>  
  
     <span data-ttu-id="edaee-172">![ボキャブラリの定義](../core/media/fd81b534-ec41-4147-b716-1e10ffc01d6f.gif "fd81b534-ec41-4147-b716-1e10ffc01d6f")</span><span class="sxs-lookup"><span data-stu-id="edaee-172">![Vocabulary Definitions](../core/media/fd81b534-ec41-4147-b716-1e10ffc01d6f.gif "fd81b534-ec41-4147-b716-1e10ffc01d6f")</span></span>  
<span data-ttu-id="edaee-173">XML のボキャブラリの定義</span><span class="sxs-lookup"><span data-stu-id="edaee-173">XML vocabulary definition</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="edaee-174">定義済みの要素およびドキュメントの種類の存在は検証されません。</span><span class="sxs-lookup"><span data-stu-id="edaee-174">The existence of the defined element and the document type is never validated.</span></span> <span data-ttu-id="edaee-175">アサートされたドキュメントが要素を持たない場合は、実行時エラーが表示されます。</span><span class="sxs-lookup"><span data-stu-id="edaee-175">If the asserted document does not have the element, you will get a runtime error.</span></span> <span data-ttu-id="edaee-176">不明なドキュメントの種類のドキュメントをアサートすると単純に無視されます。</span><span class="sxs-lookup"><span data-stu-id="edaee-176">If you assert a document with unknown document type, it will simply be ignored.</span></span>  
  
#### <a name="to-define-a-vocabulary-definition-as-a-database-table-or-database-table-column"></a><span data-ttu-id="edaee-177">ボキャブラリの定義をデータベース テーブルまたはデータベース テーブルの列として定義するには</span><span class="sxs-lookup"><span data-stu-id="edaee-177">To define a vocabulary definition as a database table or database table column</span></span>  
  
1.  <span data-ttu-id="edaee-178">ボキャブラリのバージョンを右クリックし、をクリックし、**新しい定義の追加**します。</span><span class="sxs-lookup"><span data-stu-id="edaee-178">Right-click the vocabulary version and then click **Add New Definition**.</span></span>  
  
2.  <span data-ttu-id="edaee-179">ボキャブラリの定義ウィザードで選択**データベース テーブルまたはデータベース テーブル列の定義**、順にクリックします**次**します。</span><span class="sxs-lookup"><span data-stu-id="edaee-179">In the Vocabulary Definition Wizard, select **Database Table or Database Table Column Definition**, and then click **Next**.</span></span>  
  
3.  <span data-ttu-id="edaee-180">定義の名前と定義の説明を入力します。</span><span class="sxs-lookup"><span data-stu-id="edaee-180">Type a definition name and definition description.</span></span>  
  
4.  <span data-ttu-id="edaee-181">**[参照]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="edaee-181">Click **Browse**.</span></span>  
  
5.  <span data-ttu-id="edaee-182">使用して接続する SQL Server コンピューターを選択します。</span><span class="sxs-lookup"><span data-stu-id="edaee-182">Select a SQL Server computer to connect with.</span></span> <span data-ttu-id="edaee-183">SQL Server コンピューターが現在開始されていない場合は、選択、**が停止している場合、SQL Server 開始**チェック ボックスをオンします。</span><span class="sxs-lookup"><span data-stu-id="edaee-183">If the SQL Server computer is not currently started, select the **Start SQL Server if it is stopped** check box.</span></span>  
  
6.  <span data-ttu-id="edaee-184">認証の種類を選択します。</span><span class="sxs-lookup"><span data-stu-id="edaee-184">Select an authentication type.</span></span> <span data-ttu-id="edaee-185">SQL Server 認証を選択した場合、ログオン名とパスワードを入力し、クリックして**OK**します。</span><span class="sxs-lookup"><span data-stu-id="edaee-185">If you select SQL Server authentication, type your logon name and password, and then click **OK**.</span></span>  
  
7.  <span data-ttu-id="edaee-186">テーブルまたはテーブルの列をクリックして、バインドする選択**OK**します。</span><span class="sxs-lookup"><span data-stu-id="edaee-186">Select the table or table column that you want to bind to, and then click **OK**.</span></span>  
  
8.  <span data-ttu-id="edaee-187">テーブルの列を選択した場合は、その値を取得またはその値を設定するかどうかを選択します。</span><span class="sxs-lookup"><span data-stu-id="edaee-187">If you selected a table column, select whether you want to get its value or set its value.</span></span> <span data-ttu-id="edaee-188">その値を取得する場合は、表示名を入力します。</span><span class="sxs-lookup"><span data-stu-id="edaee-188">If you choose to get its value, type the display name.</span></span> <span data-ttu-id="edaee-189">その値を設定する場合をクリックして**次**表示形式を指定します。</span><span class="sxs-lookup"><span data-stu-id="edaee-189">If you choose to set its value, click **Next** to specify the display format.</span></span>  
  
     <span data-ttu-id="edaee-190">詳細については、このトピックの"パラメーターを使用して、ボキャブラリの定義の表示形式を指定する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="edaee-190">For more information, see "To specify the display format of a vocabulary definition by using parameters" later in this topic.</span></span>  
  
9. <span data-ttu-id="edaee-191">テーブルを選択した場合は、表示名を入力します。</span><span class="sxs-lookup"><span data-stu-id="edaee-191">If you selected a table, type a display name.</span></span>  
  
10. <span data-ttu-id="edaee-192">**[完了]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="edaee-192">Click **Finish**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="edaee-193">既定では、 **DataConnection**バインディングが使用されます</span><span class="sxs-lookup"><span data-stu-id="edaee-193">By default, **DataConnection** binding is used</span></span>  
  
     <span data-ttu-id="edaee-194">![ボキャブラリの定義](../core/media/f8121306-cd73-4997-adc4-71a055dfd824.gif "f8121306-cd73-4997-adc4-71a055dfd824")</span><span class="sxs-lookup"><span data-stu-id="edaee-194">![Vocabulary Definitions](../core/media/f8121306-cd73-4997-adc4-71a055dfd824.gif "f8121306-cd73-4997-adc4-71a055dfd824")</span></span>  
<span data-ttu-id="edaee-195">データベースのボキャブラリの定義</span><span class="sxs-lookup"><span data-stu-id="edaee-195">Database vocabulary definition</span></span>  
  
#### <a name="to-specify-the-display-format-of-a-vocabulary-definition-by-using-parameters"></a><span data-ttu-id="edaee-196">パラメーターを使用して、ボキャブラリの定義の表示形式を指定するには</span><span class="sxs-lookup"><span data-stu-id="edaee-196">To specify the display format of a vocabulary definition by using parameters</span></span>  
  
1.  <span data-ttu-id="edaee-197">一覧からパラメーターを選択**パラメーター**クリックしてボキャブラリの定義ウィザードで**編集**します。</span><span class="sxs-lookup"><span data-stu-id="edaee-197">Select a parameter from the list of **Parameters** in Vocabulary Definition Wizard, and then click **Edit**.</span></span>  
  
2.  <span data-ttu-id="edaee-198">選択**定数の値を使用**定数の値を入力または選択**公開済みのボキャブラリから定義を使用**ボキャブラリの定義を参照し をクリックし、 **ok**。</span><span class="sxs-lookup"><span data-stu-id="edaee-198">Select **Use Constant Value** and enter a constant value, or select **Use Definition from a Published Vocabulary** and browse to a vocabulary definition, and then click **OK**.</span></span>  
  
3.  <span data-ttu-id="edaee-199">表示書式文字列を入力するかクリックして**既定**をクリックして既定の表示書式文字列に戻す**完了**します。</span><span class="sxs-lookup"><span data-stu-id="edaee-199">Type the display format string or click **Default** to revert to the default display format string, and then click **Finish**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="edaee-200">書式指定文字列は中かっこでパラメーターのインデックスを含める必要があります: たとえば、"{0}「と」{1}"-パラメーターのプレース ホルダーとして。</span><span class="sxs-lookup"><span data-stu-id="edaee-200">Your format string should include parameter indexes in curly braces—for example, "{0}" and "{1}"—to serve as placeholders for the parameters.</span></span>  
  
     <span data-ttu-id="edaee-201">![ボキャブラリの定義](../core/media/822f78f4-278a-4211-83ad-44032fa81f13.gif "822f78f4-278a-4211-83ad-44032fa81f13")</span><span class="sxs-lookup"><span data-stu-id="edaee-201">![Vocabulary Definitions](../core/media/822f78f4-278a-4211-83ad-44032fa81f13.gif "822f78f4-278a-4211-83ad-44032fa81f13")</span></span>  
<span data-ttu-id="edaee-202">パラメーターによるボキャブラリの定義</span><span class="sxs-lookup"><span data-stu-id="edaee-202">Vocabulary definition with parameters</span></span>