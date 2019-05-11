---
title: BizTalk フラット ファイル スキーマ ウィザードを使用する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a7cb8b18-266d-422e-bdb8-1efefb6b4c8e
caps.latest.revision: 28
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 28e0c95087c3471e29d0d487171ce30ff92d46eb
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65383580"
---
# <a name="how-to-use-biztalk-flat-file-schema-wizard"></a><span data-ttu-id="ad15e-102">BizTalk フラット ファイル スキーマ ウィザードの使用方法</span><span class="sxs-lookup"><span data-stu-id="ad15e-102">How to Use BizTalk Flat File Schema Wizard</span></span>
<span data-ttu-id="ad15e-103">BizTalk Server の以前のリリースでは、XSD (XML スキーマ定義) 言語のスキーマをフラット ファイル パイプライン コンポーネント (フラット ファイル アセンブラーやフラット ファイル逆アセンブラーなど) に認識させるには、BizTalk スキーマ エディターでスキーマに注釈を手動で追加する必要がありました。</span><span class="sxs-lookup"><span data-stu-id="ad15e-103">In previous releases of BizTalk Server, you had to manually add the annotations to XML Schema Definition language (XSD) schemas in the BizTalk Schema Editor to make these schemas understandable to Flat File Pipeline components, such as Flat File Disassembler and Flat File Assembler.</span></span> <span data-ttu-id="ad15e-104">同様の操作は、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] のスキーマ エディターでも行うことができますが、</span><span class="sxs-lookup"><span data-stu-id="ad15e-104">You can still do this using the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Schema Editor.</span></span> <span data-ttu-id="ad15e-105">ソリューションの作成で手動による操作と時間を減らすために、BizTalk フラット ファイル スキーマ ウィザードを使用することをお勧めします。このウィザードは、次の機能を備えています。</span><span class="sxs-lookup"><span data-stu-id="ad15e-105">To reduce the number of manual steps and time needed to create solutions, you use the BizTalk Flat File Schema Wizard, which provides the following functionalities:</span></span>  
  
-   <span data-ttu-id="ad15e-106">実際のフラット ファイル インスタンスを入力として使用できる機能</span><span class="sxs-lookup"><span data-stu-id="ad15e-106">Uses real flat file instances as input.</span></span>  
  
-   <span data-ttu-id="ad15e-107">区切り文字および位置指定の形式のフラット ファイル スキーマを操作するための、視覚的なデザイン画面</span><span class="sxs-lookup"><span data-stu-id="ad15e-107">Includes a visual design surface for working with delimited and positional flat file schemas.</span></span>  
  
-   <span data-ttu-id="ad15e-108">要素をスキーマに追加したり、フラット ファイル関連の注釈を定義するための、ウィザードによる対話形式の手順 (再入可能)</span><span class="sxs-lookup"><span data-stu-id="ad15e-108">Uses a re-entrant wizard-based process for adding elements to the schema and defining flat file related annotations interactively.</span></span>  
  
-   <span data-ttu-id="ad15e-109">タグ識別子、および文字による区切り記号と 16 進数による区切り記号のサポート</span><span class="sxs-lookup"><span data-stu-id="ad15e-109">Provides support for tag identifiers and character and hexadecimal delimiters.</span></span>  
  
-   <span data-ttu-id="ad15e-110">タグ識別子のオフセットおよび子区切りの順序を自動的に決定</span><span class="sxs-lookup"><span data-stu-id="ad15e-110">Automatically determines tag identifier offsets and child delimiting order.</span></span>  
  
-   <span data-ttu-id="ad15e-111">ファイル形式のプレビュー機能</span><span class="sxs-lookup"><span data-stu-id="ad15e-111">Provides preview capabilities for the file format.</span></span>  
  
-   <span data-ttu-id="ad15e-112">ユーザーが選択したインターチェンジ インスタンス内の優先サブデータを、フラット ファイル スキーマの定義に使用可能</span><span class="sxs-lookup"><span data-stu-id="ad15e-112">Enables you to select preferred sub-data within the interchange instance to use to define the flat file schemas.</span></span>  
  
## <a name="how-to-start-the-biztalk-flat-file-schema-wizard"></a><span data-ttu-id="ad15e-113">BizTalk フラット ファイル スキーマ ウィザードを開始する方法</span><span class="sxs-lookup"><span data-stu-id="ad15e-113">How to Start the BizTalk Flat File Schema Wizard</span></span>  
 <span data-ttu-id="ad15e-114">Microsoft Visual Studio ソリューション エクスプローラーまたは BizTalk スキーマ エディターのどちらを使用しても、ウィザードを開始できます。</span><span class="sxs-lookup"><span data-stu-id="ad15e-114">You can start the wizard from either the Microsoft Visual Studio Solution Explorer or from the BizTalk Schema Editor.</span></span>  
  
#### <a name="to-start-the-wizard-from-solution-explorer"></a><span data-ttu-id="ad15e-115">ソリューション エクスプローラーからウィザードを起動するには</span><span class="sxs-lookup"><span data-stu-id="ad15e-115">To start the wizard from Solution Explorer</span></span>  
  
1. <span data-ttu-id="ad15e-116">Microsoft で[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]、オープン、**ソリューション エクスプ ローラー**します。</span><span class="sxs-lookup"><span data-stu-id="ad15e-116">In Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], open the **Solution Explorer**.</span></span>  
  
2. <span data-ttu-id="ad15e-117">新しいフラット ファイル スキーマを追加するには、BizTalk プロジェクトを右クリックして**追加**します。</span><span class="sxs-lookup"><span data-stu-id="ad15e-117">To add the new flat-file schema, right-click the BizTalk project, and select **Add**.</span></span>  
  
3. <span data-ttu-id="ad15e-118">クリックして**新しい項目。**</span><span class="sxs-lookup"><span data-stu-id="ad15e-118">Click **New Item.**</span></span>  
  
    <span data-ttu-id="ad15e-119">![ソリューション エクスプ ローラー メニュー](../core/media/flatfileschemawizard-01.gif "FlatFileSchemaWizard_01")</span><span class="sxs-lookup"><span data-stu-id="ad15e-119">![Solution Explorer menu](../core/media/flatfileschemawizard-01.gif "FlatFileSchemaWizard_01")</span></span>  
  
4. <span data-ttu-id="ad15e-120">**新しい項目の追加**ウィンドウで、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="ad15e-120">In the **Add New Item** window, do the following:</span></span>  
  
   1.  <span data-ttu-id="ad15e-121">**カテゴリ**セクションで、**スキーマ ファイル**します。</span><span class="sxs-lookup"><span data-stu-id="ad15e-121">In the **Categories** section, select **Schema Files**.</span></span>  
  
   2.  <span data-ttu-id="ad15e-122">**テンプレート**セクションで、**フラット ファイル スキーマ ウィザード**します。</span><span class="sxs-lookup"><span data-stu-id="ad15e-122">In the **Templates** section, select **Flat File Schema Wizard**.</span></span>  
  
   3.  <span data-ttu-id="ad15e-123">**名前**テキスト ボックスで、新しいスキーマの名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="ad15e-123">In the **Name** text box, type a name for the new schema.</span></span>  
  
   4.  <span data-ttu-id="ad15e-124">**[追加]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ad15e-124">Click **Add**.</span></span>  
  
        <span data-ttu-id="ad15e-125">BizTalk フラット ファイル スキーマ ウィザードが開きます。</span><span class="sxs-lookup"><span data-stu-id="ad15e-125">The BizTalk Flat File Schema Wizard opens.</span></span>  
  
#### <a name="to-start-the-wizard-from-the-schema-editor"></a><span data-ttu-id="ad15e-126">スキーマ エディターからウィザードを起動するには</span><span class="sxs-lookup"><span data-stu-id="ad15e-126">To start the Wizard from the Schema Editor</span></span>  
  
1. <span data-ttu-id="ad15e-127">[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]、オープン、**ソリューション エクスプ ローラー**します。</span><span class="sxs-lookup"><span data-stu-id="ad15e-127">In [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], open the **Solution Explorer**.</span></span>  
  
2. <span data-ttu-id="ad15e-128">新しいフラット ファイル スキーマを追加するには、BizTalk プロジェクトを右クリックして**追加**します。</span><span class="sxs-lookup"><span data-stu-id="ad15e-128">To add the new flat-file schema, right-click the BizTalk project, and select **Add**.</span></span> <span data-ttu-id="ad15e-129">選択**新しい項目の** をクリック**新しい項目の**します。</span><span class="sxs-lookup"><span data-stu-id="ad15e-129">Select **New Item** and click **New Item**.</span></span>  
  
3. <span data-ttu-id="ad15e-130">**新しい項目の追加**ウィンドウで、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="ad15e-130">In the **Add New Item** window, do the following:</span></span>  
  
   1.  <span data-ttu-id="ad15e-131">**カテゴリ**セクションで、**スキーマ ファイル**します。</span><span class="sxs-lookup"><span data-stu-id="ad15e-131">In the **Categories** section, select **Schema Files**.</span></span>  
  
   2.  <span data-ttu-id="ad15e-132">**テンプレート**セクションで、**フラット ファイル スキーマ**します。</span><span class="sxs-lookup"><span data-stu-id="ad15e-132">In the **Templates** section, select **Flat File Schema**.</span></span>  
  
   3.  <span data-ttu-id="ad15e-133">**名前**テキスト ボックスで、新しいスキーマの名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="ad15e-133">In the **Name** text box, type a name for the new schema.</span></span>  
  
   4.  <span data-ttu-id="ad15e-134">**[追加]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ad15e-134">Click **Add**.</span></span>  
  
   5.  <span data-ttu-id="ad15e-135">右クリックして**ルート**選択**フラット ファイル インスタンスからレコードを定義**します。</span><span class="sxs-lookup"><span data-stu-id="ad15e-135">Right-click **Root** and select **Define Record from Flat File Instance**.</span></span>  
  
        <span data-ttu-id="ad15e-136">BizTalk フラット ファイル スキーマ ウィザードが起動します。</span><span class="sxs-lookup"><span data-stu-id="ad15e-136">The BizTalk Flat File Schema Wizard now starts.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ad15e-137">行う必要があるすべてが、選択したノードを右クリックし、スキーマ エディターで開かれる作業のスキーマがあれば、**フラット ファイル インスタンスからレコードを定義**します。</span><span class="sxs-lookup"><span data-stu-id="ad15e-137">If you have a working schema opened in the Schema Editor, all you need to do is right-click the selected node and then select **Define Record from Flat File Instance**.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ad15e-138">**フラット ファイル インスタンスからレコードを定義**オプションを有効にすると、選択したノードが子要素のないレコードの場合。</span><span class="sxs-lookup"><span data-stu-id="ad15e-138">The **Define Record from Flat File Instance** option is enabled if the selected node is a record without child elements.</span></span> <span data-ttu-id="ad15e-139">選択したノードに子要素がある場合、ウィザードでは現在のすべての子要素が削除され、新しい子要素が生成されます。</span><span class="sxs-lookup"><span data-stu-id="ad15e-139">If the selected node has child elements, the wizard deletes all current child elements and generates the new ones.</span></span> <span data-ttu-id="ad15e-140">ウィザードで既存の子要素が削除される前には確認のメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="ad15e-140">The wizard prompts you to confirm before deleting the existing child elements.</span></span>  
  
## <a name="considerations-for-using-the-flat-file-schema-wizard"></a><span data-ttu-id="ad15e-141">フラット ファイル スキーマ ウィザードを使用する上での注意点</span><span class="sxs-lookup"><span data-stu-id="ad15e-141">Considerations for Using the Flat File Schema Wizard</span></span>  
 <span data-ttu-id="ad15e-142">ここでは、BizTalk フラット ファイル スキーマ ウィザードを使用する際に考慮する必要のある問題について説明します。</span><span class="sxs-lookup"><span data-stu-id="ad15e-142">This section describes issues you should consider when working with the BizTalk Flat File Schema Wizard.</span></span>  
  
### <a name="working-with-multibyte-character-set-mbcs"></a><span data-ttu-id="ad15e-143">マルチバイト文字セット (MBCS) を使用した作業</span><span class="sxs-lookup"><span data-stu-id="ad15e-143">Working with Multibyte Character Set (MBCS)</span></span>  
 <span data-ttu-id="ad15e-144">既定では、**位置のカウント (バイト) 単位** チェック ボックスが、フラット ファイル スキーマ情報 画面でオフになっています。</span><span class="sxs-lookup"><span data-stu-id="ad15e-144">By default, the **Count positions in bytes** check box is unchecked on the Flat File Schema Information screen.</span></span> <span data-ttu-id="ad15e-145">ウィザードでは、位置は文字数でカウントされます。したがって、位置指定フラット ファイル インスタンスに MBCS 文字がある場合、その位置は正しくカウントされません。</span><span class="sxs-lookup"><span data-stu-id="ad15e-145">The wizard counts the positions by characters; which mean that if you have MBCS characters in your positional flat file instance, the positions are not counted correctly.</span></span> <span data-ttu-id="ad15e-146">選択して、**位置のカウント (バイト) 単位**チェック ボックス、ウィザードには、位置指定の長さの値が追加では MBCS 文字が表示されます。</span><span class="sxs-lookup"><span data-stu-id="ad15e-146">By selecting the **Count positions in bytes** check box, the wizard displays MBCS characters with an additional indication of their positional length.</span></span> <span data-ttu-id="ad15e-147">MBCS 文字は画面上で 1 つ分の位置となり、残りの長さはドット記号 "•" で表示されます。</span><span class="sxs-lookup"><span data-stu-id="ad15e-147">The character takes one position on the display and the remaining length is filled out with dot symbols, “•”.</span></span> <span data-ttu-id="ad15e-148">表示されるドット記号の数は、保存されたファイル形式 (2 バイト文字セット (DBCS)、Unicode または UTF-8) によって決まります。</span><span class="sxs-lookup"><span data-stu-id="ad15e-148">The number of dot symbols filled will be depending on the files that were saved in double byte character set (DBCS), Unicode or UTF-8 format.</span></span>  
  
### <a name="code-pages-supported-in-the-flat-file-schema-wizard"></a><span data-ttu-id="ad15e-149">フラット ファイル スキーマ ウィザードでサポートされるコード ページ</span><span class="sxs-lookup"><span data-stu-id="ad15e-149">Code Pages Supported in the Flat File Schema Wizard</span></span>  
 <span data-ttu-id="ad15e-150">このウィザードでサポートされるコード ページの一覧を次に示します。</span><span class="sxs-lookup"><span data-stu-id="ad15e-150">The following is a list of supported code pages for the wizard:</span></span>  
  
-   <span data-ttu-id="ad15e-151">アラビア語 (1256)</span><span class="sxs-lookup"><span data-stu-id="ad15e-151">Arabic (1256)</span></span>  
  
-   <span data-ttu-id="ad15e-152">ASCII (20127)</span><span class="sxs-lookup"><span data-stu-id="ad15e-152">ASCII (20127)</span></span>  
  
-   <span data-ttu-id="ad15e-153">バルト語 (1257)</span><span class="sxs-lookup"><span data-stu-id="ad15e-153">Baltic (1257)</span></span>  
  
-   <span data-ttu-id="ad15e-154">ビッグ エンディアン UTF16 (1201)</span><span class="sxs-lookup"><span data-stu-id="ad15e-154">Big-Endian-UTF16 (1201)</span></span>  
  
-   <span data-ttu-id="ad15e-155">中央ヨーロッパ言語 (1250)</span><span class="sxs-lookup"><span data-stu-id="ad15e-155">Central-European (1250)</span></span>  
  
-   <span data-ttu-id="ad15e-156">キリル語 (1251)</span><span class="sxs-lookup"><span data-stu-id="ad15e-156">Cyrillic (1251)</span></span>  
  
-   <span data-ttu-id="ad15e-157">ギリシャ語 (1253)</span><span class="sxs-lookup"><span data-stu-id="ad15e-157">Greek (1253)</span></span>  
  
-   <span data-ttu-id="ad15e-158">ヘブライ語 (1255)</span><span class="sxs-lookup"><span data-stu-id="ad15e-158">Hebrew (1255)</span></span>  
  
-   <span data-ttu-id="ad15e-159">日本語 Shift_JIS (932)</span><span class="sxs-lookup"><span data-stu-id="ad15e-159">Japanese-Shift-JIS (932)</span></span>  
  
-   <span data-ttu-id="ad15e-160">韓国語 (949)</span><span class="sxs-lookup"><span data-stu-id="ad15e-160">Korean (949)</span></span>  
  
-   <span data-ttu-id="ad15e-161">リトル エンディアン UTF16 (1200)</span><span class="sxs-lookup"><span data-stu-id="ad15e-161">Little-Endian-UTF16 (1200)</span></span>  
  
-   <span data-ttu-id="ad15e-162">簡体字中国語 (936)</span><span class="sxs-lookup"><span data-stu-id="ad15e-162">Simplified-Chinese-GBK (936)</span></span>  
  
-   <span data-ttu-id="ad15e-163">簡体字中国語 GB18030 (54936)</span><span class="sxs-lookup"><span data-stu-id="ad15e-163">Simplified-Chinese-GB18030 (54936)</span></span>  
  
-   <span data-ttu-id="ad15e-164">タイ語 (874)</span><span class="sxs-lookup"><span data-stu-id="ad15e-164">Thai (874)</span></span>  
  
-   <span data-ttu-id="ad15e-165">繁体字中国語 BIG5 (950)</span><span class="sxs-lookup"><span data-stu-id="ad15e-165">Traditional-Chinese-BIG5 (950)</span></span>  
  
-   <span data-ttu-id="ad15e-166">トルコ語 (1254)</span><span class="sxs-lookup"><span data-stu-id="ad15e-166">Turkish (1254)</span></span>  
  
-   <span data-ttu-id="ad15e-167">UTF-7 (65000)</span><span class="sxs-lookup"><span data-stu-id="ad15e-167">UTF-7 (65000)</span></span>  
  
-   <span data-ttu-id="ad15e-168">UTF-8 (65001)</span><span class="sxs-lookup"><span data-stu-id="ad15e-168">UTF-8 (65001)</span></span>  
  
-   <span data-ttu-id="ad15e-169">ベトナム語 (1258)</span><span class="sxs-lookup"><span data-stu-id="ad15e-169">Vietnamese (1258)</span></span>  
  
-   <span data-ttu-id="ad15e-170">西ヨーロッパ言語 (1252)</span><span class="sxs-lookup"><span data-stu-id="ad15e-170">Western-European (1252)</span></span>  
  
### <a name="record-types-in-the-flat-file-schema-wizard"></a><span data-ttu-id="ad15e-171">フラット ファイル スキーマ ウィザードでのレコードの種類</span><span class="sxs-lookup"><span data-stu-id="ad15e-171">Record Types in the Flat File Schema Wizard</span></span>  
 <span data-ttu-id="ad15e-172">フラット ファイルでは、位置指定レコード内に区切られたレコードを含めることはできません。</span><span class="sxs-lookup"><span data-stu-id="ad15e-172">Flat files cannot contain delimited records within positional records.</span></span> <span data-ttu-id="ad15e-173">ウィザードは、ベース再入可能であるため、定義するオプション ボタンの種類、**区切り記号**と**相対位置**有効または無効に親レコードの形式に基づくウィザードで定義した子。</span><span class="sxs-lookup"><span data-stu-id="ad15e-173">Because the wizard is re-entrant based, the radio buttons that define the type of the **By delimiter symbol** and **By relative positions** are enabled or disabled based on the format of the parent records for the child which you define in the wizard.</span></span> <span data-ttu-id="ad15e-174">例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="ad15e-174">For example,</span></span>  
  
-   <span data-ttu-id="ad15e-175">区切られたレコードの子に対してウィザードを実行している場合、両方のオプション ボタンが有効になります。</span><span class="sxs-lookup"><span data-stu-id="ad15e-175">If the wizard is run for a child of a delimited record, both radio buttons are selected.</span></span>  
  
-   <span data-ttu-id="ad15e-176">位置指定レコードの子に対してウィザードを実行している場合、**区切り記号**ラジオ ボタンがオフになっています。</span><span class="sxs-lookup"><span data-stu-id="ad15e-176">If the wizard is run for a child of a positional record, the **By delimiter symbol** radio button is cleared.</span></span>  
  
### <a name="delimiter-symbols-in-the-flat-file-schema-wizard"></a><span data-ttu-id="ad15e-177">フラット ファイル スキーマ ウィザードでの区切り記号</span><span class="sxs-lookup"><span data-stu-id="ad15e-177">Delimiter Symbols in the Flat File Schema Wizard</span></span>  
 <span data-ttu-id="ad15e-178">"子区切り記号" プロパティのドロップダウン リストには、次の一般的な区切り記号が表示されます。</span><span class="sxs-lookup"><span data-stu-id="ad15e-178">The child delimiter property drop-down list contains with the following common delimiters:</span></span>  
  
- <span data-ttu-id="ad15e-179">{CR}{LF}</span><span class="sxs-lookup"><span data-stu-id="ad15e-179">{CR}{LF}</span></span>  
  
- <span data-ttu-id="ad15e-180">{CR}</span><span class="sxs-lookup"><span data-stu-id="ad15e-180">{CR}</span></span>  
  
- <span data-ttu-id="ad15e-181">{LF}</span><span class="sxs-lookup"><span data-stu-id="ad15e-181">{LF}</span></span>  
  
- <span data-ttu-id="ad15e-182">{TAB}</span><span class="sxs-lookup"><span data-stu-id="ad15e-182">{TAB}</span></span>  
  
- <span data-ttu-id="ad15e-183">{SPACE}</span><span class="sxs-lookup"><span data-stu-id="ad15e-183">{SPACE}</span></span>  
  
- <span data-ttu-id="ad15e-184">{0x1A}</span><span class="sxs-lookup"><span data-stu-id="ad15e-184">{0x1A}</span></span>  
  
- <span data-ttu-id="ad15e-185">&#124;</span><span class="sxs-lookup"><span data-stu-id="ad15e-185">&#124;</span></span>  
  
- <span data-ttu-id="ad15e-186">、</span><span class="sxs-lookup"><span data-stu-id="ad15e-186">,</span></span>  
  
- <span data-ttu-id="ad15e-187">;</span><span class="sxs-lookup"><span data-stu-id="ad15e-187">;</span></span>  
  
  <span data-ttu-id="ad15e-188">このプロパティの既定値は {CR}{LF} です。</span><span class="sxs-lookup"><span data-stu-id="ad15e-188">The default value for this property is {CR}{LF}.</span></span> <span data-ttu-id="ad15e-189">このプロパティは編集可能なテキスト ボックスでもあり、子区切り記号を文字列または文字の 16 進数値として指定できます。</span><span class="sxs-lookup"><span data-stu-id="ad15e-189">The property is also an editable text box, so that you can specify the child delimiter as a sequence of characters or as hexadecimal values of the characters.</span></span> <span data-ttu-id="ad15e-190">子区切り記号に使用する文字列の例として、"a"、"street" などがあります。</span><span class="sxs-lookup"><span data-stu-id="ad15e-190">An example of using characters for the child delimiter would be "a" or "street."</span></span> <span data-ttu-id="ad15e-191">16 進数の区切り記号は次の形式を使用して指定します。</span><span class="sxs-lookup"><span data-stu-id="ad15e-191">Hexadecimal delimiters are specified using the following format:</span></span>  
  
- <span data-ttu-id="ad15e-192">{0xnnnn} : </span><span class="sxs-lookup"><span data-stu-id="ad15e-192">{0xnnnn}.</span></span> <span data-ttu-id="ad15e-193">たとえば、{0x0D} {0x0A} {0} 0x09 または 0x20 {0}。</span><span class="sxs-lookup"><span data-stu-id="ad15e-193">For example, {0x0D}{0x0A}, {0x09} or {0x20}.</span></span>  
  
  <span data-ttu-id="ad15e-194">連続した 16 進数値を使用する場合の例としては、{0x0D}{0x0A}、{0x09}{0x20} などがあります。</span><span class="sxs-lookup"><span data-stu-id="ad15e-194">An example of using sequence of hexadecimal values is {0x0D}{0x0A}, {0x09}{0x20}.</span></span>  
  
  <span data-ttu-id="ad15e-195">記号を使用する場合\\、{、または}、区切り記号として区切り記号の前に円記号を配置する必要があります、それ以外の場合、エラー メッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="ad15e-195">If you use the symbols \\, {, or } as the delimiter, you must place an additional backslash symbol in front of the delimiter symbol, otherwise you will receive an error message.</span></span> <span data-ttu-id="ad15e-196">例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="ad15e-196">For example,</span></span>  
  
- <span data-ttu-id="ad15e-197">\\\\、 \\{、または\\}。</span><span class="sxs-lookup"><span data-stu-id="ad15e-197">\\\\, \\{, or \\}.</span></span>  
  
### <a name="relative-positions-in-the-flat-file-schema-wizard"></a><span data-ttu-id="ad15e-198">フラット ファイル スキーマ ウィザードでの相対位置</span><span class="sxs-lookup"><span data-stu-id="ad15e-198">Relative Positions in the Flat File Schema Wizard</span></span>  
  
#### <a name="setting-position-markers"></a><span data-ttu-id="ad15e-199">位置マーカーの設定</span><span class="sxs-lookup"><span data-stu-id="ad15e-199">Setting Position Markers</span></span>  
 <span data-ttu-id="ad15e-200">マウスの左ボタンを使用して、新しい位置マーカー線を設定する位置の選択ボックス内の位置マーカーをクリックします。</span><span class="sxs-lookup"><span data-stu-id="ad15e-200">Use the left mouse button to click a position marker in the position selection box to set the new position marker line.</span></span> <span data-ttu-id="ad15e-201">位置マーカーは実線で表されます。</span><span class="sxs-lookup"><span data-stu-id="ad15e-201">The position marker is represented as a solid line.</span></span> <span data-ttu-id="ad15e-202">既定では、位置マーカー線はレコードの先頭であるゼロ位置にあります。</span><span class="sxs-lookup"><span data-stu-id="ad15e-202">By default, a position marker line exists at the beginning of the record at position zero.</span></span> <span data-ttu-id="ad15e-203">既存の位置マーカー線を削除するには、マウスの左ボタンを使用してそれをクリックします。</span><span class="sxs-lookup"><span data-stu-id="ad15e-203">To remove an existing position marker line, use the left mouse button to click  it.</span></span>  
  
### <a name="escape-characters-in-the-flat-file-schema-wizard"></a><span data-ttu-id="ad15e-204">フラット ファイル スキーマ ウィザードでのエスケープ文字</span><span class="sxs-lookup"><span data-stu-id="ad15e-204">Escape Characters in the Flat File Schema Wizard</span></span>  
 <span data-ttu-id="ad15e-205">エスケープ文字とは、特殊な意味を持つ文字の前に置くことによって、その意味を無効化させることのできる単一の文字のことです。</span><span class="sxs-lookup"><span data-stu-id="ad15e-205">An escape character is a single character that suppresses any special meaning of the character that follows it.</span></span> <span data-ttu-id="ad15e-206">詳細については、次を参照してください。[エスケープ文字](../core/escape-characters.md)トピックの「[フィールド値の一部としての特殊文字の解釈方法](../core/ways-to-interpret-special-characters-as-part-of-a-field-value.md)します。</span><span class="sxs-lookup"><span data-stu-id="ad15e-206">For more information, see [Escape Characters](../core/escape-characters.md) topic under [Ways to Interpret Special Characters as Part of a Field Value](../core/ways-to-interpret-special-characters-as-part-of-a-field-value.md).</span></span> <span data-ttu-id="ad15e-207">ウィザードで "エスケープ文字" プロパティを使用すると、フラット ファイル インスタンスの解析時に使用するエスケープ文字を指定できます。</span><span class="sxs-lookup"><span data-stu-id="ad15e-207">You use the escape character property in the wizard to specify the escape character to use when parsing the flat file instance.</span></span> <span data-ttu-id="ad15e-208">既定値は NULL です。つまり、スキーマ レベルで定義されてた既定のエスケープ文字が使用されます。</span><span class="sxs-lookup"><span data-stu-id="ad15e-208">The default is null, meaning that the default escape character defined at the schema level is used.</span></span>  
  
 <span data-ttu-id="ad15e-209">エスケープ文字には、文字値または 16 進数値を指定できます。</span><span class="sxs-lookup"><span data-stu-id="ad15e-209">The escape character can be specified as a character or as a hexadecimal value.</span></span> <span data-ttu-id="ad15e-210">16 進数値として指定する場合は、次の形式を使用します。</span><span class="sxs-lookup"><span data-stu-id="ad15e-210">The hexadecimal value is specified using the following format:</span></span>  
  
- <span data-ttu-id="ad15e-211">{0xnnnn} : </span><span class="sxs-lookup"><span data-stu-id="ad15e-211">{0xnnnn}.</span></span> <span data-ttu-id="ad15e-212">たとえば、{0x0D}{0x0A}、{0x09}、{0x20} のように指定します。</span><span class="sxs-lookup"><span data-stu-id="ad15e-212">For example, {0x0D}{0x0A}, {0x09}, or {0x20}.</span></span>  
  
  <span data-ttu-id="ad15e-213">記号を使用する場合\\、{、または}、エスケープ文字として区切り記号の前に円記号を配置する必要があります、それ以外の場合は表示されるエラー メッセージなど</span><span class="sxs-lookup"><span data-stu-id="ad15e-213">If you use the symbols \\, {, or } as the escape character, you must place an additional backslash symbol in front of the delimiter symbol, otherwise you will receive an error message For example,</span></span>  
  
- <span data-ttu-id="ad15e-214">\\\\, \\{, \\}.</span><span class="sxs-lookup"><span data-stu-id="ad15e-214">\\\\, \\{, \\}.</span></span>  
  
### <a name="child-elements-in-the-flat-file-schema-wizard"></a><span data-ttu-id="ad15e-215">フラット ファイル スキーマ ウィザードでの子要素</span><span class="sxs-lookup"><span data-stu-id="ad15e-215">Child Elements in the Flat File Schema Wizard</span></span>  
 <span data-ttu-id="ad15e-216">各子要素を含む**要素名**、**要素型**、**データ型**と**コンテンツ**します。</span><span class="sxs-lookup"><span data-stu-id="ad15e-216">Each child element contains **Element Name**, **Element Type**, **Data Type** and **Content**.</span></span> <span data-ttu-id="ad15e-217">使用する、**要素名**テキスト ボックスに、ノードの意味のある名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="ad15e-217">You use the **Element Name** text box to type a meaningful name for the node.</span></span> <span data-ttu-id="ad15e-218">**要素型**は次の値がドロップダウン リストです。</span><span class="sxs-lookup"><span data-stu-id="ad15e-218">The **Element Type** is a drop-down list with the following values:</span></span>  
  
- <span data-ttu-id="ad15e-219">**フィールド要素**:このノードがスキーマ内の要素として作成することを指定します。</span><span class="sxs-lookup"><span data-stu-id="ad15e-219">**Field element**: Specifies that this node will be created in the schema as an element.</span></span>  
  
- <span data-ttu-id="ad15e-220">**フィールド属性**:このノードが属性として、スキーマで作成することを指定します。</span><span class="sxs-lookup"><span data-stu-id="ad15e-220">**Field attribute**: Specifies that this node will be created in the schema as an attribute.</span></span>  
  
- <span data-ttu-id="ad15e-221">**レコード**:スキーマの子のないレコードが作成されることを指定します。</span><span class="sxs-lookup"><span data-stu-id="ad15e-221">**Record**: Specifies that a record without children will be created in the schema.</span></span>  
  
- <span data-ttu-id="ad15e-222">**繰り返しレコード**:スキーマの子を持たないレコードを作成するが、最大出現数に設定されていることを指定します**Unbounded**します。</span><span class="sxs-lookup"><span data-stu-id="ad15e-222">**Repeating record**: Specifies that a record without children will be created in the schema and its max occurrence is set to **Unbounded**.</span></span>  
  
- <span data-ttu-id="ad15e-223">**無視**:このノードのスキーマで何も作成されます。</span><span class="sxs-lookup"><span data-stu-id="ad15e-223">**Ignore**: Nothing will be created in the schema for this node.</span></span>  
  
  <span data-ttu-id="ad15e-224">既定ですべての要素は、型の**フィールド要素**し、そのデータ型は**文字列**します。</span><span class="sxs-lookup"><span data-stu-id="ad15e-224">By default all elements are of type **Field element** and their data type is **string**.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ad15e-225">子要素として宣言することができます、**フィールド属性**として宣言されているその前に子が存在しない場合にのみ**要素フィールド**、**レコード**または**繰り返しレコード**します。</span><span class="sxs-lookup"><span data-stu-id="ad15e-225">A child element can be declared as a **Field attribute** only if there are no children before it that are declared as **Field elements**, **Record** or **Repeating record**.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ad15e-226">前に感嘆符が表示されます、**子ノード**で、次のインスタンス。</span><span class="sxs-lookup"><span data-stu-id="ad15e-226">You will see an exclamation mark in front of the **child nodes** in the following instances:</span></span>  
  
-   <span data-ttu-id="ad15e-227">**フィールド属性**後に定義されて**フィールド要素**、**レコード、** または**繰り返しレコード**します。</span><span class="sxs-lookup"><span data-stu-id="ad15e-227">The **Field attribute** is defined after **Field element**, **Record,** or **Repeating record**.</span></span>  
  
-   <span data-ttu-id="ad15e-228">子要素に名前がない。</span><span class="sxs-lookup"><span data-stu-id="ad15e-228">The child element does not have a name.</span></span>  
  
-   <span data-ttu-id="ad15e-229">子要素の名前が重複している。</span><span class="sxs-lookup"><span data-stu-id="ad15e-229">The child element has a duplicate name.</span></span>  
  
-   <span data-ttu-id="ad15e-230">子要素に選択されているデータ型が、内容に対して適切ではない。</span><span class="sxs-lookup"><span data-stu-id="ad15e-230">The selected data type for the child element is not suitable for the content.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ad15e-231">参照</span><span class="sxs-lookup"><span data-stu-id="ad15e-231">See Also</span></span>  
 [<span data-ttu-id="ad15e-232">BizTalk フラット ファイル スキーマ ウィザードのチュートリアル</span><span class="sxs-lookup"><span data-stu-id="ad15e-232">BizTalk Flat File Schema Wizard Walkthrough</span></span>](../core/biztalk-flat-file-schema-wizard-walkthrough.md)