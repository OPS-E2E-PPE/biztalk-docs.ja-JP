---
title: 'チュートリアル: ドキュメント インスタンスからフラット ファイル スキーマの作成 |Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a5e1453f-0380-4505-97a9-9d3526db0923
caps.latest.revision: 47
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: faa79ea6784df39bb2f06b32b289837093a04919
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36983427"
---
# <a name="walkthrough-creating-a-flat-file-schema-from-a-document-instance"></a><span data-ttu-id="11ccf-102">チュートリアル: ドキュメント インスタンスからフラット ファイル スキーマの作成</span><span class="sxs-lookup"><span data-stu-id="11ccf-102">Walkthrough: Creating a Flat File Schema From a Document Instance</span></span>
<span data-ttu-id="11ccf-103">このチュートリアルでは、BizTalk フラット ファイル スキーマ ウィザードを使用してドキュメント インスタンスからフラット ファイル スキーマを作成する方法について説明します。ここでは注文書のサンプルを使用します。</span><span class="sxs-lookup"><span data-stu-id="11ccf-103">This walkthrough shows you how to create a flat file schema from a document instance using the BizTalk Flat File Schema Wizard based on the following sample purchase order.</span></span> <span data-ttu-id="11ccf-104">BizTalk フラット ファイル スキーマ ウィザードの概要については、次を参照してください。 [BizTalk フラット ファイル スキーマ ウィザードを使用する方法](../core/how-to-use-biztalk-flat-file-schema-wizard.md)します。</span><span class="sxs-lookup"><span data-stu-id="11ccf-104">For an introduction to the BizTalk Flat File Schema Wizard, see [How to Use BizTalk Flat File Schema Wizard](../core/how-to-use-biztalk-flat-file-schema-wizard.md).</span></span>  

 <span data-ttu-id="11ccf-105">![サンプルの注文書](../core/media/flatfileschema-samplepurchaseorder.gif "FlatFileSchema_SamplePurchaseOrder")</span><span class="sxs-lookup"><span data-stu-id="11ccf-105">![Sample Purchase Order](../core/media/flatfileschema-samplepurchaseorder.gif "FlatFileSchema_SamplePurchaseOrder")</span></span>  

 <span data-ttu-id="11ccf-106">注文書の各行は、復帰と改行 (CRLF) で終わります。この部分は緑色で表されます。</span><span class="sxs-lookup"><span data-stu-id="11ccf-106">Each line of the purchase order ends with a carriage return line feed (CRLF), marked in green.</span></span> <span data-ttu-id="11ccf-107">注文書は PO タグで始まります。このタグは赤色で表され、後に日付が続きます。</span><span class="sxs-lookup"><span data-stu-id="11ccf-107">The purchase order starts with a PO tag shown in red and followed by a date.</span></span> <span data-ttu-id="11ccf-108">2 回繰り返される固定の位置指定フィールドには顧客情報が含まれます。このフィールドは紫色で表されます。</span><span class="sxs-lookup"><span data-stu-id="11ccf-108">Two repeating fixed positional fields contain customer information and are shown in purple.</span></span> <span data-ttu-id="11ccf-109">コメント フィールドの後に、複数のコンマ (,) で区切られたレコードとパイプ (&#124;) で区切られたデータ値を含む、ITEMS タグで始まる反復的フィールドは、青で表示します。</span><span class="sxs-lookup"><span data-stu-id="11ccf-109">After the comment field, there is a repeating field starting with an ITEMS tag that contains multiple records delimited by commas (,) and data values separated by pipes (&#124;), which are shown in blue.</span></span>  

## <a name="prerequisites"></a><span data-ttu-id="11ccf-110">前提条件</span><span class="sxs-lookup"><span data-stu-id="11ccf-110">Prerequisites</span></span>  
 <span data-ttu-id="11ccf-111">このチュートリアルを実行する前には、サーバー上に次のソフトウェアがインストールされ構成されていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="11ccf-111">Before exercising this walkthrough, make sure the following software is installed and configured on your server:</span></span>  

- <span data-ttu-id="11ccf-112">Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="11ccf-112">Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]</span></span>  

- <span data-ttu-id="11ccf-113">Microsoft[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]で、 **Developer tools**インストール</span><span class="sxs-lookup"><span data-stu-id="11ccf-113">Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] with the **Developer tools** installed</span></span>

  <span data-ttu-id="11ccf-114">チュートリアルでは、ドキュメント インスタンスを準備するには、以下の内容をテキスト エディターにコピーし、テキスト ファイルとして保存します。</span><span class="sxs-lookup"><span data-stu-id="11ccf-114">To prepare the document instance for the walkthrough, copy the following into a text editor, and save it as a text file.</span></span> <span data-ttu-id="11ccf-115">すべての行をコピーするには、フィードおよび改行を必ずします。</span><span class="sxs-lookup"><span data-stu-id="11ccf-115">Be sure to copy all line feeds and carriage returns.</span></span>  

```
PO1999-10-20
US        Alice Smith         123 Maple Street    Mill Valley    CA 90952
US        Robert Smith        8 Oak Avenue        Old Town       PA 95819
ITEMS,ITEM872-AA|Lawnmower|1|148.95|Confirm this is electric,ITEM926-AA|Baby Monitor|1|39.98|Confirm this is electric
```


## <a name="start-the-wizard"></a><span data-ttu-id="11ccf-116">ウィザードを開始する</span><span class="sxs-lookup"><span data-stu-id="11ccf-116">Start the wizard</span></span>  

1. <span data-ttu-id="11ccf-117">[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]、オープン、**ソリューション エクスプ ローラー**します。</span><span class="sxs-lookup"><span data-stu-id="11ccf-117">In [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], open the **Solution Explorer**.</span></span>  

2. <span data-ttu-id="11ccf-118">新しいフラット ファイル スキーマを追加するには、プロジェクトを右クリックして**追加**します。</span><span class="sxs-lookup"><span data-stu-id="11ccf-118">To add the new flat file schema, right-click the project, and select **Add**.</span></span> <span data-ttu-id="11ccf-119">クリックして**新しい項目の**します。</span><span class="sxs-lookup"><span data-stu-id="11ccf-119">Click **New Item**.</span></span>  

3. <span data-ttu-id="11ccf-120">**新しい項目の追加**ウィンドウで、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="11ccf-120">In the **Add New Item** window, do the following:</span></span>  

   1.  <span data-ttu-id="11ccf-121">**カテゴリ**セクションで、**スキーマ ファイル**します。</span><span class="sxs-lookup"><span data-stu-id="11ccf-121">In the **Categories** section, select **Schema Files**.</span></span>  

   2.  <span data-ttu-id="11ccf-122">**テンプレート**セクションで、**フラット ファイル スキーマ ウィザード**します。</span><span class="sxs-lookup"><span data-stu-id="11ccf-122">In the **Templates** section, select **Flat File Schema Wizard**.</span></span>  

   3.  <span data-ttu-id="11ccf-123">**名前**フィールドに、入力**PurchaseOrder.xsd**新しいスキーマ。</span><span class="sxs-lookup"><span data-stu-id="11ccf-123">In the **Name** field, enter **PurchaseOrder.xsd** for the new schema.</span></span>  

   4.  <span data-ttu-id="11ccf-124">**[追加]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="11ccf-124">Click **Add**.</span></span>  

4. <span data-ttu-id="11ccf-125">BizTalk フラット ファイル スキーマ ウィザードが開くと、[ようこそ] ページが表示されます。</span><span class="sxs-lookup"><span data-stu-id="11ccf-125">When the BizTalk Flat File Schema Wizard opens, the Welcome Page appears.</span></span>   
   <span data-ttu-id="11ccf-126">今後ウィザードを実行している場合は、この画面をスキップするには、選択、**このはじめに ページを今後表示しない**ボックス。</span><span class="sxs-lookup"><span data-stu-id="11ccf-126">To skip this screen when running the wizard in the future, select the **Do not show this introduction page again** box.</span></span> <span data-ttu-id="11ccf-127">**[次へ]** をクリックして次に進みます。</span><span class="sxs-lookup"><span data-stu-id="11ccf-127">Click **Next** to continue.</span></span>  

## <a name="selecting-purchase-order-instance"></a><span data-ttu-id="11ccf-128">注文書インスタンスを選択します。</span><span class="sxs-lookup"><span data-stu-id="11ccf-128">Selecting purchase order instance</span></span>  

-   <span data-ttu-id="11ccf-129">**フラット ファイル スキーマ情報**画面で、インスタンスを選択して、次の情報を入力します。</span><span class="sxs-lookup"><span data-stu-id="11ccf-129">On the **Flat File Schema Information** screen, select your instance and enter the following information.</span></span> <span data-ttu-id="11ccf-130">完了したら、クリックして **[次へ]** を続行します。</span><span class="sxs-lookup"><span data-stu-id="11ccf-130">When you are done, click **Next** to continue.</span></span>  

    -   <span data-ttu-id="11ccf-131">**インスタンスのファイル:**  をクリックして、**参照**フラット ファイル スキーマの生成元を指定するボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="11ccf-131">**Instance file:** Click the **Browse** button to locate the flat file from which the schema will be generated.</span></span> <span data-ttu-id="11ccf-132">チュートリアルの前提条件」セクションで作成したテキスト ファイルを含むフォルダーを参照: フラット ファイル スキーマから、ドキュメント インスタンスを作成します。</span><span class="sxs-lookup"><span data-stu-id="11ccf-132">Browse to the folder containing the text file you created in the Prerequisites section of Walkthrough: Creating a Flat File Schema From a Document Instance.</span></span>  

    -   <span data-ttu-id="11ccf-133">**レコード名:** 型**PO**スキーマのルート名になります。</span><span class="sxs-lookup"><span data-stu-id="11ccf-133">**Record name:** Type **PO** as it will be the schema root name.</span></span>  

    -   <span data-ttu-id="11ccf-134">**ターゲットの名前空間:** 型**http://Flat_File_Project.PurchaseOrder**スキーマのターゲット名前空間。</span><span class="sxs-lookup"><span data-stu-id="11ccf-134">**Target namespace:** Type **http://Flat_File_Project.PurchaseOrder** for schema target namespace.</span></span>  

    -   <span data-ttu-id="11ccf-135">**コード ページ:** 選択**utf-8 (65001)** ドロップダウン リストから。</span><span class="sxs-lookup"><span data-stu-id="11ccf-135">**Code page:** Select **UTF-8 (65001)** from the drop down selection list.</span></span>  

    -   <span data-ttu-id="11ccf-136">**位置のカウント (バイト) 単位:** バイトで位置指定データ フィールドをカウントする場合、チェック ボックスをオンします。</span><span class="sxs-lookup"><span data-stu-id="11ccf-136">**Count positions in bytes:** Check this box if you wish to count the positional data fields by bytes.</span></span> <span data-ttu-id="11ccf-137">既定では、位置指定データ フィールドは文字数でカウントされます。</span><span class="sxs-lookup"><span data-stu-id="11ccf-137">By default, the positional data fields are counted in characters.</span></span> <span data-ttu-id="11ccf-138">このチュートリアルをそのまま、**位置のカウント (バイト) 単位**チェック ボックスはオフです。</span><span class="sxs-lookup"><span data-stu-id="11ccf-138">In this walkthrough, leave the **Count positions in bytes** check box unchecked.</span></span>  

## <a name="select-purchase-order-data"></a><span data-ttu-id="11ccf-139">注文書データを選択します。</span><span class="sxs-lookup"><span data-stu-id="11ccf-139">Select purchase order data</span></span>  

-   <span data-ttu-id="11ccf-140">**ドキュメント データを選択**画面、フラット ファイルの内容が表示されます。</span><span class="sxs-lookup"><span data-stu-id="11ccf-140">On the **Select Document Data** screen, the contents of the flat file are displayed.</span></span> <span data-ttu-id="11ccf-141">スキーマを作成するために必要なデータを選択し、クリックして**次**します。</span><span class="sxs-lookup"><span data-stu-id="11ccf-141">Select the data needed for creating the schema, and then click **Next**.</span></span>  

    > [!NOTE]
    >  <span data-ttu-id="11ccf-142">キーを押してドキュメント インスタンス全体を使用する場合は、 **CTRL + A**すべてを選択します。</span><span class="sxs-lookup"><span data-stu-id="11ccf-142">If you would like to use the entire document instance, you can press **Ctrl-A** to select all.</span></span>  

    > [!NOTE]
    >  <span data-ttu-id="11ccf-143">確認**長い行を折り返す**ウィザードにおいて編集ボックスにラップされたドキュメント全体のインスタンスのコンテンツを表示する場合します。</span><span class="sxs-lookup"><span data-stu-id="11ccf-143">Check **Wrap long lines** box if you want to view the entire document instance content wrapped into the edit box throughout the wizard.</span></span>  

    > [!NOTE]
    >  <span data-ttu-id="11ccf-144">インターチェンジ インスタンスからスキーマを作成する場合は、個別のドキュメント構造を表す部分のみを選択します。</span><span class="sxs-lookup"><span data-stu-id="11ccf-144">If you are creating the schema from an interchange instance, select only the part that represents the individual document structure.</span></span>  

## <a name="delimit-purchase-order-record"></a><span data-ttu-id="11ccf-145">注文書レコードを区切り</span><span class="sxs-lookup"><span data-stu-id="11ccf-145">Delimit purchase order record</span></span>  

-   <span data-ttu-id="11ccf-146">ライン フィード (CRLF) で、注文の各行のキャリッジ リターンが終わると、選択**区切り記号**、順にクリックします**次**で**レコード書式を**画面。</span><span class="sxs-lookup"><span data-stu-id="11ccf-146">As each line of the purchase order ends with a carriage return line feed (CRLF), select **By delimiter symbol**, and then click **Next** on **Select Record Format** screen.</span></span>  

## <a name="specify-purchase-order-record-property"></a><span data-ttu-id="11ccf-147">購買注文レコードのプロパティを指定します。</span><span class="sxs-lookup"><span data-stu-id="11ccf-147">Specify purchase order record property</span></span>  

- <span data-ttu-id="11ccf-148">**区切られたレコード**画面で、スキーマの最初のレベルを定義し、終えたらをクリックするには、次を入力します。**次**します。</span><span class="sxs-lookup"><span data-stu-id="11ccf-148">On the **Delimited Record** screen, enter the following to define the first level of the schema and when you are done, click **Next**.</span></span>  

  - <span data-ttu-id="11ccf-149">**子区切り記号:** 選択 **{CR} {LF}** します。</span><span class="sxs-lookup"><span data-stu-id="11ccf-149">**Child delimiter:** Select **{CR}{LF}**.</span></span>  

    > [!NOTE]
    >  <span data-ttu-id="11ccf-150">**子区切り記号**プロパティは、編集可能なドロップダウン リスト ボックスには、既定値のセットが含まれています。</span><span class="sxs-lookup"><span data-stu-id="11ccf-150">**Child delimiter** property is an editable box with drop down selection list contains a set of default values.</span></span> <span data-ttu-id="11ccf-151">**子区切り記号**文字、または 16 進数の値として指定することができます。</span><span class="sxs-lookup"><span data-stu-id="11ccf-151">The **Child delimiter** can be specified as a character or as a hexadecimal value.</span></span> <span data-ttu-id="11ccf-152">たとえば、  **\\{** または **{0x0d0a}** します。</span><span class="sxs-lookup"><span data-stu-id="11ccf-152">For example, **\\{** or **{0x0D0A}**.</span></span>  

  - <span data-ttu-id="11ccf-153">**エスケープ文字:** エスケープ文字がそれに続く文字の特殊な意味を抑制する単一の文字。</span><span class="sxs-lookup"><span data-stu-id="11ccf-153">**Escape character:** An escape character is a single character that suppresses any special meaning of the character that follows it.</span></span> <span data-ttu-id="11ccf-154">参照してください[エスケープ文字](../core/escape-characters.md)詳細についてはします。</span><span class="sxs-lookup"><span data-stu-id="11ccf-154">See [Escape Characters](../core/escape-characters.md) for more information.</span></span> <span data-ttu-id="11ccf-155">このチュートリアルでは空白のままにします。</span><span class="sxs-lookup"><span data-stu-id="11ccf-155">Leave it blank for the walkthrough.</span></span>  

    > [!NOTE]
    >  <span data-ttu-id="11ccf-156">使用する場合**\\**、 **{、** と **}** の**子区切り記号**または**エスケープ文字**、バック スラッシュを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="11ccf-156">When using **\\**, **{,** and **}** for **Child delimiter** or **Escape character**, a back slash must be used.</span></span> <span data-ttu-id="11ccf-157">たとえば、  **\\ \\、** と **\\{** します。</span><span class="sxs-lookup"><span data-stu-id="11ccf-157">For example, **\\\\,** and **\\{**.</span></span>  

  - <span data-ttu-id="11ccf-158">確認**レコードにタグ識別子**ボックス**PO**で**タグ**します。</span><span class="sxs-lookup"><span data-stu-id="11ccf-158">Check **Record has a tag identifier** box and type **PO** in **Tag**.</span></span> <span data-ttu-id="11ccf-159">複数のレコード ファイルで**PO**個々 のレコードを識別するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="11ccf-159">In a multiple records file, **PO** will be used to identify each individual record.</span></span> <span data-ttu-id="11ccf-160">**[次へ]** をクリックして次に進みます。</span><span class="sxs-lookup"><span data-stu-id="11ccf-160">Click **Next** to continue.</span></span>  

    <span data-ttu-id="11ccf-161">![区切られたレコード 画面](../core/media/flatfileschemawizard-delimitedrecord1.gif "FlatFileSchemaWizard_DelimitedRecord1")</span><span class="sxs-lookup"><span data-stu-id="11ccf-161">![Delimited Record screen](../core/media/flatfileschemawizard-delimitedrecord1.gif "FlatFileSchemaWizard_DelimitedRecord1")</span></span>  

## <a name="define-the-element-in-the-purchase-order-record"></a><span data-ttu-id="11ccf-162">注文書レコード内の要素を定義します。</span><span class="sxs-lookup"><span data-stu-id="11ccf-162">Define the element in the purchase order record</span></span>  

1.  <span data-ttu-id="11ccf-163">ウィザードのここまでの作業で、注文書レコードの 4 つの要素を指定しました。次は、要素のプロパティを定義する必要があります。</span><span class="sxs-lookup"><span data-stu-id="11ccf-163">The wizard has identified four elements in the purchase order record; you must now define the element property.</span></span> <span data-ttu-id="11ccf-164">最初の行で、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="11ccf-164">In the first row, do the following:</span></span>  

    1.  <span data-ttu-id="11ccf-165">型**日付**の**要素名**します。</span><span class="sxs-lookup"><span data-stu-id="11ccf-165">Type **date** for the **Element Name**.</span></span>  

    2.  <span data-ttu-id="11ccf-166">選択**フィールド要素**の**要素型**します。</span><span class="sxs-lookup"><span data-stu-id="11ccf-166">Select **Field element** for **Element Type**.</span></span>  

    3.  <span data-ttu-id="11ccf-167">選択**日付**のドロップダウン リストから**データ型**します。</span><span class="sxs-lookup"><span data-stu-id="11ccf-167">Select **date** from the drop-down selection list for **Data Type**.</span></span>  

2.  <span data-ttu-id="11ccf-168">次の要素について手順 a ～ c を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="11ccf-168">Repeat Steps a to c for the following elements.</span></span> <span data-ttu-id="11ccf-169">完了したら、クリックして**次**します。</span><span class="sxs-lookup"><span data-stu-id="11ccf-169">When you are done, click **Next**.</span></span>  

    |<span data-ttu-id="11ccf-170">要素名</span><span class="sxs-lookup"><span data-stu-id="11ccf-170">Element Name</span></span>|<span data-ttu-id="11ccf-171">[要素の種類]</span><span class="sxs-lookup"><span data-stu-id="11ccf-171">Element Type</span></span>|<span data-ttu-id="11ccf-172">データ型</span><span class="sxs-lookup"><span data-stu-id="11ccf-172">Data Type</span></span>|  
    |------------------|------------------|---------------|  
    |<span data-ttu-id="11ccf-173">**顧客**</span><span class="sxs-lookup"><span data-stu-id="11ccf-173">**customer**</span></span>|<span data-ttu-id="11ccf-174">**繰り返しレコード**</span><span class="sxs-lookup"><span data-stu-id="11ccf-174">**Repeating record**</span></span>||  
    ||<span data-ttu-id="11ccf-175">**無視します。**</span><span class="sxs-lookup"><span data-stu-id="11ccf-175">**Ignore**</span></span>||  
    |<span data-ttu-id="11ccf-176">**項目**</span><span class="sxs-lookup"><span data-stu-id="11ccf-176">**items**</span></span>|<span data-ttu-id="11ccf-177">**レコード**</span><span class="sxs-lookup"><span data-stu-id="11ccf-177">**Record**</span></span>||  

     <span data-ttu-id="11ccf-178">![子要素 画面](../core/media/flatfileschemawizard-childelements.gif "FlatFileSchemaWizard_ChildElements")</span><span class="sxs-lookup"><span data-stu-id="11ccf-178">![Child Elements screen](../core/media/flatfileschemawizard-childelements.gif "FlatFileSchemaWizard_ChildElements")</span></span>  

    > [!NOTE]
    >  <span data-ttu-id="11ccf-179">複数の行を選択し、変更することができます、**要素型**マウスと shift キーまたは CTRL キーを使用して単一の型にします。</span><span class="sxs-lookup"><span data-stu-id="11ccf-179">You can select multiple rows and then change their **Element Type** to a single type by using the mouse and the SHIFT or CTRL key.</span></span>  

    > [!NOTE]
    >  <span data-ttu-id="11ccf-180">クリックした後**次へ**上、**子要素** 画面で、をクリックしてできません**戻る**を再定義したり、子要素を変更することです。</span><span class="sxs-lookup"><span data-stu-id="11ccf-180">After you click **Next** on the **Child Elements** screen, you will not be able to click **Back** to redefine or make any changes to the child elements.</span></span> <span data-ttu-id="11ccf-181">子要素を再定義または変更するには、ウィザードを終了し、もう一度ウィザードを起動してフラット ファイルを定義する必要があります。</span><span class="sxs-lookup"><span data-stu-id="11ccf-181">You may need to close the wizard and launch the wizard again to define the flat file schema.</span></span>  

3.  <span data-ttu-id="11ccf-182">以上の手順を完了すると、次に示すようにスキーマの最初のレベルが生成されます。</span><span class="sxs-lookup"><span data-stu-id="11ccf-182">After you complete the steps in this procedure, the first level of the schema is generated as shown in the following screenshot.</span></span> <span data-ttu-id="11ccf-183">ここでは 3 つの一意な要素が定義されています。この後で、注文書レコード内の要素の子レコードを定義します。</span><span class="sxs-lookup"><span data-stu-id="11ccf-183">Three unique elements are defined, and you will continue to further define the child records for the elements in the purchase order record.</span></span> <span data-ttu-id="11ccf-184">**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="11ccf-184">Click **Next**.</span></span>  

     <span data-ttu-id="11ccf-185">![サンプル スキーマ 画面](../core/media/flatfileschemawizard-schema1.gif "FlatFileSchemaWizard_Schema1")</span><span class="sxs-lookup"><span data-stu-id="11ccf-185">![Sample Schema screen](../core/media/flatfileschemawizard-schema1.gif "FlatFileSchemaWizard_Schema1")</span></span>  

## <a name="define-the-customer-record"></a><span data-ttu-id="11ccf-186">顧客レコードを定義します。</span><span class="sxs-lookup"><span data-stu-id="11ccf-186">Define the customer record</span></span>  

1.  <span data-ttu-id="11ccf-187">定義したため、**顧客**要素として、**繰り返しレコード**型と**項目**要素として、**レコード**BizTalk を入力します。フラット ファイル スキーマ ウィザードで引き続きさらにこれら 2 つの要素を定義します。</span><span class="sxs-lookup"><span data-stu-id="11ccf-187">Because we defined the **customer** element as the **Repeating record** type and the **items** element as the **Record** type, the BizTalk Flat File Schema Wizard now continues to further define these two elements.</span></span> <span data-ttu-id="11ccf-188">**スキーマ ビュー**画面で、**顧客**、順にクリックします**次へ**を続行します。</span><span class="sxs-lookup"><span data-stu-id="11ccf-188">On the **Schema View** screen, select **customer**, and then click **Next** to continue.</span></span>  

2.  <span data-ttu-id="11ccf-189">顧客レコードを操作するには、要素を表すデータを選択する必要があります。</span><span class="sxs-lookup"><span data-stu-id="11ccf-189">To work with the customer record, you need to select the data that represents that element.</span></span> <span data-ttu-id="11ccf-190">このレコードは繰り返しレコードなので、任意の行を使用してレコードを定義できます。</span><span class="sxs-lookup"><span data-stu-id="11ccf-190">Because it is a repeating record, either of the lines can be used to define the record.</span></span> <span data-ttu-id="11ccf-191">顧客データの最初の行を選択し、クリックして**次**を続行します。</span><span class="sxs-lookup"><span data-stu-id="11ccf-191">Select the first line of customer data and click **Next** to continue.</span></span>  

3.  <span data-ttu-id="11ccf-192">**レコード書式を**ページで、選択**相対位置**、順にクリックします**次**します。</span><span class="sxs-lookup"><span data-stu-id="11ccf-192">On the **Select Record Format** page, select **By relative positions**, and then click **Next**.</span></span>  

4.  <span data-ttu-id="11ccf-193">このウィザードでは、フィールドの間隔を表示および計算するためのビジュアル ツールを利用できます。</span><span class="sxs-lookup"><span data-stu-id="11ccf-193">The wizard provides a visual tool for showing and calculating the distance between the fields.</span></span> <span data-ttu-id="11ccf-194">**位置指定レコード** ページで、マウスの左ボタンを使用して、名前 フィールドの開始位置を表す位置マーカー 10 をクリックします。</span><span class="sxs-lookup"><span data-stu-id="11ccf-194">On the **Positional Record** page, use the left mouse button to click the position marker 10 to represent where the name field begins.</span></span> <span data-ttu-id="11ccf-195">次の位置マーカーを残りのデータ フィールドをクリックします。</span><span class="sxs-lookup"><span data-stu-id="11ccf-195">Click the following position markers to represent the rest of the data fields:</span></span>  

    |<span data-ttu-id="11ccf-196">フィールド名</span><span class="sxs-lookup"><span data-stu-id="11ccf-196">Field Name</span></span>|<span data-ttu-id="11ccf-197">位置マーカー</span><span class="sxs-lookup"><span data-stu-id="11ccf-197">Position Marker</span></span>|  
    |----------------|---------------------|  
    |<span data-ttu-id="11ccf-198">street</span><span class="sxs-lookup"><span data-stu-id="11ccf-198">street</span></span>|<span data-ttu-id="11ccf-199">30</span><span class="sxs-lookup"><span data-stu-id="11ccf-199">30</span></span>|  
    |<span data-ttu-id="11ccf-200">city</span><span class="sxs-lookup"><span data-stu-id="11ccf-200">city</span></span>|<span data-ttu-id="11ccf-201">50</span><span class="sxs-lookup"><span data-stu-id="11ccf-201">50</span></span>|  
    |<span data-ttu-id="11ccf-202">state</span><span class="sxs-lookup"><span data-stu-id="11ccf-202">state</span></span>|<span data-ttu-id="11ccf-203">65</span><span class="sxs-lookup"><span data-stu-id="11ccf-203">65</span></span>|  
    |<span data-ttu-id="11ccf-204">postalcode</span><span class="sxs-lookup"><span data-stu-id="11ccf-204">postalcode</span></span>|<span data-ttu-id="11ccf-205">68</span><span class="sxs-lookup"><span data-stu-id="11ccf-205">68</span></span>|  

     <span data-ttu-id="11ccf-206">**[次へ]** をクリックして次に進みます。</span><span class="sxs-lookup"><span data-stu-id="11ccf-206">Click **Next** to continue.</span></span>  

     <span data-ttu-id="11ccf-207">![位置指定レコード 画面](../core/media/flatfileschemawizard-positionalrecord.gif "FlatFileSchemaWizard_PositionalRecord")</span><span class="sxs-lookup"><span data-stu-id="11ccf-207">![Positional Record screen](../core/media/flatfileschemawizard-positionalrecord.gif "FlatFileSchemaWizard_PositionalRecord")</span></span>  

5.  <span data-ttu-id="11ccf-208">**子要素** ページで、子要素のプロパティを指定します。</span><span class="sxs-lookup"><span data-stu-id="11ccf-208">On the **Child Elements** page, you specify the properties of the child elements.</span></span> <span data-ttu-id="11ccf-209">最初の行と種類を選択**国**として、**要素名**します。</span><span class="sxs-lookup"><span data-stu-id="11ccf-209">Select the first row and type **country** as the **Element Name**.</span></span> <span data-ttu-id="11ccf-210">他の列では既定値をそのまま使用します。</span><span class="sxs-lookup"><span data-stu-id="11ccf-210">Leave the default values in the other columns.</span></span> <span data-ttu-id="11ccf-211">次の他のプロパティの値を入力、**要素名**:</span><span class="sxs-lookup"><span data-stu-id="11ccf-211">Type the following values for the other properties for the **Element Name**:</span></span>  

    |<span data-ttu-id="11ccf-212">要素名</span><span class="sxs-lookup"><span data-stu-id="11ccf-212">Element Name</span></span>|<span data-ttu-id="11ccf-213">値</span><span class="sxs-lookup"><span data-stu-id="11ccf-213">Value</span></span>|  
    |------------------|-----------|  
    |<span data-ttu-id="11ccf-214">**customer_Child2**</span><span class="sxs-lookup"><span data-stu-id="11ccf-214">**customer_Child2**</span></span>|<span data-ttu-id="11ccf-215">**fullName**</span><span class="sxs-lookup"><span data-stu-id="11ccf-215">**fullName**</span></span>|  
    |<span data-ttu-id="11ccf-216">**customer_Child3**</span><span class="sxs-lookup"><span data-stu-id="11ccf-216">**customer_Child3**</span></span>|<span data-ttu-id="11ccf-217">**番地**</span><span class="sxs-lookup"><span data-stu-id="11ccf-217">**street**</span></span>|  
    |<span data-ttu-id="11ccf-218">**customer_Child4**</span><span class="sxs-lookup"><span data-stu-id="11ccf-218">**customer_Child4**</span></span>|<span data-ttu-id="11ccf-219">**市区町村**</span><span class="sxs-lookup"><span data-stu-id="11ccf-219">**city**</span></span>|  
    |<span data-ttu-id="11ccf-220">**customer_Child5**</span><span class="sxs-lookup"><span data-stu-id="11ccf-220">**customer_Child5**</span></span>|<span data-ttu-id="11ccf-221">**state**</span><span class="sxs-lookup"><span data-stu-id="11ccf-221">**state**</span></span>|  
    |<span data-ttu-id="11ccf-222">**customer_Child6**</span><span class="sxs-lookup"><span data-stu-id="11ccf-222">**customer_Child6**</span></span>|<span data-ttu-id="11ccf-223">**[郵便番号]**</span><span class="sxs-lookup"><span data-stu-id="11ccf-223">**postalcode**</span></span>|  

     <span data-ttu-id="11ccf-224">**[次へ]** をクリックして次に進みます。</span><span class="sxs-lookup"><span data-stu-id="11ccf-224">Click **Next** to continue.</span></span>  

     <span data-ttu-id="11ccf-225">![子要素 画面](../core/media/flatfileschemawizard-childelements2.gif "FlatFileSchemaWizard_ChildElements2")</span><span class="sxs-lookup"><span data-stu-id="11ccf-225">![Child Elements screen](../core/media/flatfileschemawizard-childelements2.gif "FlatFileSchemaWizard_ChildElements2")</span></span>  

6.  <span data-ttu-id="11ccf-226">次に示すように、顧客レコードの子要素が作成されます。</span><span class="sxs-lookup"><span data-stu-id="11ccf-226">The child elements of the customer record are created as shown in the following screenshot.</span></span> <span data-ttu-id="11ccf-227">をクリックして**次**品目レコードの子要素を定義します。</span><span class="sxs-lookup"><span data-stu-id="11ccf-227">Click **Next** to define the child elements for the items record.</span></span>  

     <span data-ttu-id="11ccf-228">![サンプル スキーマ 画面](../core/media/flatfileschemawizard-schema2.gif "FlatFileSchemaWizard_Schema2")</span><span class="sxs-lookup"><span data-stu-id="11ccf-228">![Sample Schema screen](../core/media/flatfileschemawizard-schema2.gif "FlatFileSchemaWizard_Schema2")</span></span>  

#### <a name="define-the-items-record"></a><span data-ttu-id="11ccf-229">品目レコードを定義します。</span><span class="sxs-lookup"><span data-stu-id="11ccf-229">Define the items record</span></span>  

1. <span data-ttu-id="11ccf-230">**スキーマ ビュー** ] ページで、[**項目**、順にクリックします**次**します。</span><span class="sxs-lookup"><span data-stu-id="11ccf-230">On the **Schema View** page, select **items**, and then click **Next**.</span></span>  

2. <span data-ttu-id="11ccf-231">**ドキュメント データを選択**ページで、行全体が項目では、開始し、をクリックし、選択**次**その子要素を定義します。</span><span class="sxs-lookup"><span data-stu-id="11ccf-231">On the **Select Document Data** page, select the entire line begins with ITEMS, and then click **Next** to define its child elements.</span></span>  

3. <span data-ttu-id="11ccf-232">**レコード書式を** ページで **区切り記号**、順にクリックします**次**。</span><span class="sxs-lookup"><span data-stu-id="11ccf-232">On the **Select Record Format** page, select **By delimiter symbol**, and then click **Next**.</span></span>  

4. <span data-ttu-id="11ccf-233">品目レコードでは、個々の品目の区切りにコンマを使用します。</span><span class="sxs-lookup"><span data-stu-id="11ccf-233">In the Items record, commas are used to delimit the individual items.</span></span> <span data-ttu-id="11ccf-234">そのため、上、**区切られたレコード**ページで、品目レコードを定義するには、次を入力します。</span><span class="sxs-lookup"><span data-stu-id="11ccf-234">Therefore, on the **Delimited Record** page, enter the following to define the items record.</span></span> <span data-ttu-id="11ccf-235">完了したら、クリックして**次**します。</span><span class="sxs-lookup"><span data-stu-id="11ccf-235">When you are done, click **Next**.</span></span>  

   -   <span data-ttu-id="11ccf-236">選択 **、** から**子区切り記号**ドロップダウンの選択リスト。</span><span class="sxs-lookup"><span data-stu-id="11ccf-236">Select **,** from **Child delimiter** drop-down selection list.</span></span>  

   -   <span data-ttu-id="11ccf-237">ままに、**エスケープ文字**空白テキスト ボックス。</span><span class="sxs-lookup"><span data-stu-id="11ccf-237">Leave the **Escape character** text box blank.</span></span>  

   -   <span data-ttu-id="11ccf-238">選択**レコードにタグ識別子**と種類**項目**で**タグ**します。</span><span class="sxs-lookup"><span data-stu-id="11ccf-238">Select **Record has a tag identifier** and type **ITEMS** in **Tag**.</span></span>  

        <span data-ttu-id="11ccf-239">複数の items レコードで**項目**個々 のレコードを識別するために使用します。</span><span class="sxs-lookup"><span data-stu-id="11ccf-239">In a multiple items record, **ITEMS** is used to identify each individual record.</span></span>  

5. <span data-ttu-id="11ccf-240">値を使用して、**区切られたレコード** ページで、ウィザードは、2 つの子要素を識別します。</span><span class="sxs-lookup"><span data-stu-id="11ccf-240">Using the values from the **Delimited Record** page, the wizard identifies two child elements.</span></span> <span data-ttu-id="11ccf-241">繰り返しレコードはそれらのいずれかであるため、最初の要素を選択し、入力**項目**要素名、および選択**繰り返しレコード**、ドロップ ダウン リストから**要素の型**.</span><span class="sxs-lookup"><span data-stu-id="11ccf-241">Because one of them is a repeating record, select the first element and enter **item** for Element Name, and then select **Repeating Record** from the drop down selection list for **Element Type**.</span></span> <span data-ttu-id="11ccf-242">残りの列の値は既定値のまま使用します。</span><span class="sxs-lookup"><span data-stu-id="11ccf-242">Leave the rest of the default values in the columns.</span></span> <span data-ttu-id="11ccf-243">2 番目の行を選択し、選択、**無視**から**要素型**一覧。</span><span class="sxs-lookup"><span data-stu-id="11ccf-243">Select the second row and select the **Ignore** from **Element Type** list.</span></span> <span data-ttu-id="11ccf-244">クリックすると**次**、品目レコードの次のレベルは、スキーマで作成されます。</span><span class="sxs-lookup"><span data-stu-id="11ccf-244">When you click **Next**, the next level for the items record is created in the schema.</span></span> <span data-ttu-id="11ccf-245">続けて、注文書スキーマの最後の部分を定義します。</span><span class="sxs-lookup"><span data-stu-id="11ccf-245">You continue to define the final part of the purchase order schema.</span></span>  

6. <span data-ttu-id="11ccf-246">選択**項目**順にクリックします**次**を続行する、**スキーマ ビュー**ページ。</span><span class="sxs-lookup"><span data-stu-id="11ccf-246">Select **item** and then click **Next** to continue on the **Schema View** page.</span></span>  

7. <span data-ttu-id="11ccf-247">**[ドキュメント データ** ] ページで選択 **ITEM872-AA&#124;文字です。芝刈り機&#124;1&#124;148.95&#124;文字です。これが電気確認**します。</span><span class="sxs-lookup"><span data-stu-id="11ccf-247">On the **Select Document Data** page, select **ITEM872-AA&#124;Lawnmower&#124;1&#124;148.95&#124;Confirm this is electric**.</span></span> <span data-ttu-id="11ccf-248">**[次へ]** をクリックして次に進みます。</span><span class="sxs-lookup"><span data-stu-id="11ccf-248">Click **Next** to continue.</span></span>  

8. <span data-ttu-id="11ccf-249">**レコード書式** ページで、選択、 **区切り記号** 個々 の項目が、パイプ (&#124;) で区切られたオプションを指定します。</span><span class="sxs-lookup"><span data-stu-id="11ccf-249">On the **Select Record Format** page, select the **By delimiter symbol** option because the individual item is delimited by a pipe (&#124;).</span></span>  

9. <span data-ttu-id="11ccf-250">**区切られたレコード**ページで、品目レコードを定義するには、次を入力します。</span><span class="sxs-lookup"><span data-stu-id="11ccf-250">On the **Delimited Record** page, enter the following to define the item record.</span></span> <span data-ttu-id="11ccf-251">完了したら、クリックして**次**します。</span><span class="sxs-lookup"><span data-stu-id="11ccf-251">When you are done, click **Next**.</span></span>  

    -   <span data-ttu-id="11ccf-252">選択 **&#124;** から、 **子区切り記号** ドロップダウン リストです。</span><span class="sxs-lookup"><span data-stu-id="11ccf-252">Select **&#124;** from the **Child delimiter** drop down selection list.</span></span>  

    -   <span data-ttu-id="11ccf-253">ままに、**エスケープ文字**空白テキスト ボックス。</span><span class="sxs-lookup"><span data-stu-id="11ccf-253">Leave the **Escape character** text box blank.</span></span>  

10. <span data-ttu-id="11ccf-254">**子要素** ページで、ウィザードが 5 つの子要素を識別します。</span><span class="sxs-lookup"><span data-stu-id="11ccf-254">On the **Child Elements** page, the wizard has identified five child elements.</span></span> <span data-ttu-id="11ccf-255">最初の行を選択し、入力**productCode**の**要素名**します。</span><span class="sxs-lookup"><span data-stu-id="11ccf-255">Select the first row and enter **productCode** for **Element name**.</span></span> <span data-ttu-id="11ccf-256">残りの列では既定値をそのまま使用します。</span><span class="sxs-lookup"><span data-stu-id="11ccf-256">Leave the default values in the rest of the columns.</span></span> <span data-ttu-id="11ccf-257">残りの部分、**要素名のプロパティ**次を入力します。</span><span class="sxs-lookup"><span data-stu-id="11ccf-257">For the rest of the **Element Name properties**, type the following:</span></span>  

    |<span data-ttu-id="11ccf-258">要素名</span><span class="sxs-lookup"><span data-stu-id="11ccf-258">Element Name</span></span>|<span data-ttu-id="11ccf-259">値</span><span class="sxs-lookup"><span data-stu-id="11ccf-259">Value</span></span>|  
    |------------------|-----------|  
    |<span data-ttu-id="11ccf-260">**item_Child2**</span><span class="sxs-lookup"><span data-stu-id="11ccf-260">**item_Child2**</span></span>|<span data-ttu-id="11ccf-261">**description**</span><span class="sxs-lookup"><span data-stu-id="11ccf-261">**description**</span></span>|  
    |<span data-ttu-id="11ccf-262">**item_Child3**</span><span class="sxs-lookup"><span data-stu-id="11ccf-262">**item_Child3**</span></span>|<span data-ttu-id="11ccf-263">**数量**</span><span class="sxs-lookup"><span data-stu-id="11ccf-263">**quantity**</span></span>|  
    |<span data-ttu-id="11ccf-264">**item_Child4**</span><span class="sxs-lookup"><span data-stu-id="11ccf-264">**item_Child4**</span></span>|<span data-ttu-id="11ccf-265">**unitPrice**</span><span class="sxs-lookup"><span data-stu-id="11ccf-265">**unitPrice**</span></span>|  
    |<span data-ttu-id="11ccf-266">**item_Child5**</span><span class="sxs-lookup"><span data-stu-id="11ccf-266">**item_Child5**</span></span>|<span data-ttu-id="11ccf-267">**ノート**</span><span class="sxs-lookup"><span data-stu-id="11ccf-267">**notes**</span></span>|  

     <span data-ttu-id="11ccf-268">**[次へ]** をクリックして次に進みます。</span><span class="sxs-lookup"><span data-stu-id="11ccf-268">Click **Next** to continue.</span></span>  

11. <span data-ttu-id="11ccf-269">これで、注文書スキーマのすべてのノードを定義しました。</span><span class="sxs-lookup"><span data-stu-id="11ccf-269">You have defined all the nodes for the purchase order schema.</span></span> <span data-ttu-id="11ccf-270">**スキーマ ビュー** ] ページで [**完了**します。</span><span class="sxs-lookup"><span data-stu-id="11ccf-270">On the **Schema View** page, click **Finish**.</span></span>  

12. <span data-ttu-id="11ccf-271">これで、最終的な注文書スキーマを表示できます。</span><span class="sxs-lookup"><span data-stu-id="11ccf-271">You can now view the final purchase order schema.</span></span> <span data-ttu-id="11ccf-272">BizTalk スキーマ エディターでスキーマの定義を更新することもできます。</span><span class="sxs-lookup"><span data-stu-id="11ccf-272">You can also refine the schema by using the BizTalk Schema Editor.</span></span> <span data-ttu-id="11ccf-273">フラット ファイル プロパティの名前のテーブルとプロパティ テーブルを参照してください**スキーマのノード プロパティ**します。</span><span class="sxs-lookup"><span data-stu-id="11ccf-273">See Flat file property name table and the Property tables in **Schema Node Properties**.</span></span> <span data-ttu-id="11ccf-274">このプロパティについて詳しく[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]します。</span><span class="sxs-lookup"><span data-stu-id="11ccf-274">More details on this property [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].</span></span>

## <a name="summary"></a><span data-ttu-id="11ccf-275">まとめ</span><span class="sxs-lookup"><span data-stu-id="11ccf-275">Summary</span></span>  
 <span data-ttu-id="11ccf-276">このチュートリアルでは、BizTalk フラット ファイル スキーマ ウィザードを使用して、ドキュメント インスタンスからフラット ファイル スキーマを作成する方法について学習しました。</span><span class="sxs-lookup"><span data-stu-id="11ccf-276">In this walkthrough you have learned how to use the BizTalk Flat File Schema Wizard to create a flat file schema from a document instance.</span></span>  

## <a name="next-steps"></a><span data-ttu-id="11ccf-277">次の手順</span><span class="sxs-lookup"><span data-stu-id="11ccf-277">Next Steps</span></span>  

### <a name="validate-po-instance"></a><span data-ttu-id="11ccf-278">PO インスタンスを検証します。</span><span class="sxs-lookup"><span data-stu-id="11ccf-278">Validate PO Instance</span></span>  
 <span data-ttu-id="11ccf-279">PurchaseOrder.xsd スキーマで適切に PO インスタンスが解析されることを確認するには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="11ccf-279">To ensure that the PurchaseOrder.xsd schema can correctly parse the PO instance, do the following:</span></span>  

1.  <span data-ttu-id="11ccf-280">ソリューション エクスプ ローラーで右クリックし、 **PurchaseOrder.xsd**選び**プロパティ**します。</span><span class="sxs-lookup"><span data-stu-id="11ccf-280">In Solution Explorer, right-click the **PurchaseOrder.xsd** and then select **Properties**.</span></span>  

2.  <span data-ttu-id="11ccf-281">**プロパティ ページ**、ことを確認、**入力インスタンス ファイル名**フィールドは、チュートリアルの前提条件」セクションで作成した PO インスタンスの場所を指している: フラット ファイルを作成します。ドキュメント インスタンスからスキーマです。</span><span class="sxs-lookup"><span data-stu-id="11ccf-281">In the **Property Pages**, make sure that the **Input Instance Filename** field is pointing to the location of the PO instance you created in the Prerequisites section of Walkthrough: Creating a Flat File Schema From a Document Instance.</span></span> <span data-ttu-id="11ccf-282">クリックして**OK**ダイアログ ボックスを閉じます。</span><span class="sxs-lookup"><span data-stu-id="11ccf-282">Click **OK** to close the dialog.</span></span>  

3.  <span data-ttu-id="11ccf-283">ソリューション エクスプ ローラーで右クリックして**PurchaseOrder.xsd**、し、**インスタンスの検証**です。</span><span class="sxs-lookup"><span data-stu-id="11ccf-283">In Solution Explorer, right-click **PurchaseOrder.xsd**, and then select **Validate Instance**.</span></span> <span data-ttu-id="11ccf-284">検証コンポーネントが開きます。</span><span class="sxs-lookup"><span data-stu-id="11ccf-284">The validation component opens.</span></span>  

4.  <span data-ttu-id="11ccf-285">検証が完了すると、PurchaseOrder.xsd スキーマによる PO インスタンスの解析結果に基づいた XML 出力を確認するためのリンクが表示されます。</span><span class="sxs-lookup"><span data-stu-id="11ccf-285">After validation is completed, a link is provided to you for viewing the XML output based on parsing result on PO instance using the PurchaseOrder.xsd schema.</span></span> <span data-ttu-id="11ccf-286">この XML 出力を表示するには、Ctrl キーを押しながらリンクをクリックします。</span><span class="sxs-lookup"><span data-stu-id="11ccf-286">To view the XML output, press Ctrl and click the link.</span></span>  

### <a name="create-pipelines-for-the-schema"></a><span data-ttu-id="11ccf-287">スキーマのパイプラインを作成します。</span><span class="sxs-lookup"><span data-stu-id="11ccf-287">Create Pipelines for the Schema</span></span>  
 <span data-ttu-id="11ccf-288">ここで、BizTalk アプリケーションで使用するための、PurchaseOrder.xsd スキーマに基づく受信パイプラインまたは送信パイプラインを作成できます。</span><span class="sxs-lookup"><span data-stu-id="11ccf-288">Now you can create a receive or send pipeline based on the PurchaseOrder.xsd schema to use with your BizTalk application.</span></span>  

 <span data-ttu-id="11ccf-289">新しいパイプラインを作成するを参照してください。[新しいパイプラインを作成する方法](../core/how-to-create-a-new-pipeline.md)します。</span><span class="sxs-lookup"><span data-stu-id="11ccf-289">To create a new pipeline, see [How to Create a New Pipeline](../core/how-to-create-a-new-pipeline.md).</span></span> <span data-ttu-id="11ccf-290">フラット ファイル パイプライン コンポーネントを構成するを参照してください。[フラット ファイル アセンブラー パイプライン コンポーネントを構成する方法](../core/how-to-configure-the-flat-file-assembler-pipeline-component.md)と[フラット ファイル逆アセンブラー パイプライン コンポーネントを構成する方法](../core/how-to-configure-the-flat-file-disassembler-pipeline-component.md)します。</span><span class="sxs-lookup"><span data-stu-id="11ccf-290">To configure the Flat File Pipeline components, see [How to Configure the Flat File Assembler Pipeline Component](../core/how-to-configure-the-flat-file-assembler-pipeline-component.md) and [How to Configure the Flat File Disassembler Pipeline Component](../core/how-to-configure-the-flat-file-disassembler-pipeline-component.md).</span></span>  

## <a name="see-also"></a><span data-ttu-id="11ccf-291">参照</span><span class="sxs-lookup"><span data-stu-id="11ccf-291">See Also</span></span>  
 <span data-ttu-id="11ccf-292">[BizTalk フラット ファイル スキーマ ウィザードを使用する方法](../core/how-to-use-biztalk-flat-file-schema-wizard.md) </span><span class="sxs-lookup"><span data-stu-id="11ccf-292">[How to Use BizTalk Flat File Schema Wizard](../core/how-to-use-biztalk-flat-file-schema-wizard.md) </span></span>  
 [<span data-ttu-id="11ccf-293">BizTalk フラット ファイル スキーマ ウィザードでのスキーマの作成</span><span class="sxs-lookup"><span data-stu-id="11ccf-293">Creating Schemas Using BizTalk Flat File Schema Wizard</span></span>](../core/creating-schemas-using-biztalk-flat-file-schema-wizard.md)