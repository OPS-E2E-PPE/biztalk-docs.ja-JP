---
title: 一般的な質問と回答のトラブルシューティング |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d2f89d92-0a97-4017-8b8e-6afd8b20eaf4
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6a47cfd0bc1d2de1ad044712c12b97260981e610
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37010651"
---
# <a name="general-troubleshooting-questions-and-answers"></a><span data-ttu-id="18431-102">一般的なトラブルシューティングに関する質問と回答</span><span class="sxs-lookup"><span data-stu-id="18431-102">General Troubleshooting Questions and Answers</span></span>
<span data-ttu-id="18431-103">このトピックでは、質問と回答は、BizTalk マッパーに関する問題を解決するためには。</span><span class="sxs-lookup"><span data-stu-id="18431-103">This topic has questions and answers to help you resolve issues with the BizTalk Mapper.</span></span>  
  
## <a name="how-do-i-specify-xslt-output-settings"></a><span data-ttu-id="18431-104">XSLT 出力の設定を指定する方法を教えてください。</span><span class="sxs-lookup"><span data-stu-id="18431-104">How do I specify XSLT output settings?</span></span>  
 <span data-ttu-id="18431-105">BizTalk マッパーで、XML 宣言を含めるかどうかを指定し、出力インスタンス データで使用するエンコードを制御できます。</span><span class="sxs-lookup"><span data-stu-id="18431-105">You can use the BizTalk Mapper to include or omit XML declarations, and control the encoding used for output instance data.</span></span>  
  
#### <a name="include-or-exclude-an-xml-declaration"></a><span data-ttu-id="18431-106">含めるか、XML 宣言を除外</span><span class="sxs-lookup"><span data-stu-id="18431-106">Include or exclude an XML declaration</span></span>  
  
1.  <span data-ttu-id="18431-107">グリッド ビューで、マッパー グリッドをクリックします。</span><span class="sxs-lookup"><span data-stu-id="18431-107">In the Grid view, click the mapper grid.</span></span> <span data-ttu-id="18431-108">**プロパティ**ウィンドウ グリッドのプロパティを表示します。</span><span class="sxs-lookup"><span data-stu-id="18431-108">The **Properties** window displays the grid properties.</span></span>  
  
2.  <span data-ttu-id="18431-109">ドロップダウン リストで、 **XML 宣言の省略**プロパティで、 **[はい]** 、XML 宣言を省略するか選択**いいえ**XML 宣言を省略するされません。</span><span class="sxs-lookup"><span data-stu-id="18431-109">In the drop-down list for the **Omit XML Declaration** property, select **Yes** to omit an XML declaration, or select **No** not to omit an XML declaration.</span></span>  
  
#### <a name="set-encoding-for-output-instance-data"></a><span data-ttu-id="18431-110">出力インスタンス データのエンコーディングを設定します。</span><span class="sxs-lookup"><span data-stu-id="18431-110">Set encoding for output instance data</span></span>  
  
1.  <span data-ttu-id="18431-111">グリッド ビューで、マッパー グリッドをクリックします。</span><span class="sxs-lookup"><span data-stu-id="18431-111">In the Grid view, click the mapper grid.</span></span> <span data-ttu-id="18431-112">**プロパティ**ウィンドウ グリッドのプロパティを表示します。</span><span class="sxs-lookup"><span data-stu-id="18431-112">The **Properties** window displays the grid properties.</span></span>  
  
2.  <span data-ttu-id="18431-113">ドロップダウン リストで、 **XSLT エンコード**出力インスタンス データに使用するプロパティ、文字セットを選択します。</span><span class="sxs-lookup"><span data-stu-id="18431-113">In the drop-down list for the **XSLT Encoding** property, select the character set you want to use for the output instance data.</span></span>  
  
## <a name="how-do-i-create-multipart-mappings"></a><span data-ttu-id="18431-114">マルチパート マッピングを作成するにはどうすればよいですか。</span><span class="sxs-lookup"><span data-stu-id="18431-114">How do I create multipart mappings?</span></span>  
 <span data-ttu-id="18431-115">同時に使用される複数のマップがある場合は、オーケストレーションを使用してそれらを結合する必要があります、**変換**図形を同時にテストします。</span><span class="sxs-lookup"><span data-stu-id="18431-115">If you have multiple maps that are used together, you will need to combine them in an orchestration by using the **Transform** shape to test them together.</span></span> <span data-ttu-id="18431-116">BizTalk マッパーで一度にテストできるのは 1 つのマップだけです。</span><span class="sxs-lookup"><span data-stu-id="18431-116">The BizTalk Mapper can test only one map at a time.</span></span>  
  
## <a name="why-isnt-my-database-functoid-working"></a><span data-ttu-id="18431-117">データベース Functoid が動作しないのはなぜですか。</span><span class="sxs-lookup"><span data-stu-id="18431-117">Why isn't my database functoid working?</span></span>  
 <span data-ttu-id="18431-118">データベース functoid**データベース検索**と**値抽出**; のエラー情報を直接返さないではなく、情報をキャプチャしを指定、**エラーを返す** functoid、マップで使用します。</span><span class="sxs-lookup"><span data-stu-id="18431-118">The database functoids **Database Lookup** and **Value Extractor** do not directly return error information; rather, they capture the information and supply it to the **Error Return** functoid for use by your map.</span></span> <span data-ttu-id="18431-119">使用することができます、**エラーを返す**functoid は次のシナリオと同様に、エラー検出のため。</span><span class="sxs-lookup"><span data-stu-id="18431-119">You can use the **Error Return** functoid for error detection as in the following scenarios:</span></span>  
  
- <span data-ttu-id="18431-120">マップの場合に、**データベース検索**または**値抽出**functoid は期待どおりに動作するいないとしています。</span><span class="sxs-lookup"><span data-stu-id="18431-120">When your map has a **Database Lookup** or **Value Extractor** functoid that is not behaving as expected.</span></span> <span data-ttu-id="18431-121">エラー メッセージを表示するには、この Functoid を出力スキーマのフィールドに一時的にマップしてください。</span><span class="sxs-lookup"><span data-stu-id="18431-121">To see the error message, temporarily map the functoid to a field in the output schema.</span></span>  
  
- <span data-ttu-id="18431-122">データベース操作が失敗したときに、アプリケーションで別のメッセージ内容が要求された場合。</span><span class="sxs-lookup"><span data-stu-id="18431-122">If your application expects different message content when database operations fail.</span></span> <span data-ttu-id="18431-123">使用することができます、**エラーを返す**functoid をエラーが検出され、ダウン ストリーム アプリケーションが適切な方法で対応できるように、エラー メッセージを代替構造にマップします。</span><span class="sxs-lookup"><span data-stu-id="18431-123">You can use the **Error Return** functoid to detect an error and map the error message to an alternate structure so that downstream applications can react in a controlled manner.</span></span>  
  
  <span data-ttu-id="18431-124">実行時にしか検出されないエラーを回避することを確認最初のパラメーター、**エラーを返す**functoid の出力を**データベース検索**functoid とその他の functoid での出力ではない、データベースのカテゴリ。</span><span class="sxs-lookup"><span data-stu-id="18431-124">To avoid errors that are detected only at run time, make sure that the first parameter to the **Error Return** functoid is the output of a **Database Lookup** functoid and not the output of any other functoid in the Database category.</span></span>  
  
  <span data-ttu-id="18431-125">使用しての詳細については、**エラーを返す**functoid (サンプルを含む) を参照してください、 **Functoid リファレンス**[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]します。</span><span class="sxs-lookup"><span data-stu-id="18431-125">For more information about using the **Error Return** functoid (including a sample), see the **Functoid Reference** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].</span></span>
  
## <a name="why-is-my-map-failing-when-calling-my-custom-functoid"></a><span data-ttu-id="18431-126">カスタム Functoid を呼び出すとマップで障害が発生するのはなぜですか。</span><span class="sxs-lookup"><span data-stu-id="18431-126">Why is my map failing when calling my custom functoid?</span></span>  
 <span data-ttu-id="18431-127">マップでカスタム Functoid を呼び出せるようにするには、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] コンピューターのグローバル アセンブリ キャッシュ (GAC) にそれらのカスタム Functoid をインストールしておく必要があります。</span><span class="sxs-lookup"><span data-stu-id="18431-127">Custom functoids must be installed into the global assembly cache (GAC) on the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] computer before they can be invoked by a map.</span></span> <span data-ttu-id="18431-128">カスタム Functoid を含むアセンブリが署名されており、GAC に配置されていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="18431-128">Verify that the assembly containing your custom functoid has been signed and placed into the GAC.</span></span> <span data-ttu-id="18431-129">また、アセンブリを "%BTSINSTALLPATH%\Developer Tools\Mapper Extensions" フォルダーにコピーします。</span><span class="sxs-lookup"><span data-stu-id="18431-129">Also, copy the assembly into the folder “%BTSINSTALLPATH%\Developer Tools\Mapper Extensions”.</span></span>  
  
 <span data-ttu-id="18431-130">アセンブリを GAC にインストールの詳細については、次を参照してください。 [GAC でアセンブリのインストール](../core/assembly-installation-in-the-gac.md)します。</span><span class="sxs-lookup"><span data-stu-id="18431-130">For more information about installing assemblies to the GAC, see [Assembly Installation in the GAC](../core/assembly-installation-in-the-gac.md).</span></span> <span data-ttu-id="18431-131">GAC にインストールされたアセンブリを表示するには、[!INCLUDE[btsWinNoVersion](../includes/btswinnoversion-md.md)] のインストール ディレクトリの Assembly ディレクトリに移動します。</span><span class="sxs-lookup"><span data-stu-id="18431-131">To view assemblies installed in the GAC, navigate to the Assembly directory of your [!INCLUDE[btsWinNoVersion](../includes/btswinnoversion-md.md)] installation directory.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="18431-132">参照</span><span class="sxs-lookup"><span data-stu-id="18431-132">See Also</span></span>  
 [<span data-ttu-id="18431-133">マップのトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="18431-133">Troubleshooting Maps</span></span>](../core/troubleshooting-maps.md)