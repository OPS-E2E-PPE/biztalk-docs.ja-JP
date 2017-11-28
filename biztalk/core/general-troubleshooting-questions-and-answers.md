---
title: "一般的な質問と回答のトラブルシューティング |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d2f89d92-0a97-4017-8b8e-6afd8b20eaf4
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 37e63f8838dea7adee91b5b43b2bc881cb53eae1
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="general-troubleshooting-questions-and-answers"></a><span data-ttu-id="e119d-102">一般的なトラブルシューティングに関する質問と回答</span><span class="sxs-lookup"><span data-stu-id="e119d-102">General Troubleshooting Questions and Answers</span></span>
<span data-ttu-id="e119d-103">このトピックには質問と回答は、BizTalk マッパーでの問題を解決するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="e119d-103">This topic has questions and answers to help you resolve issues with the BizTalk Mapper.</span></span>  
  
## <a name="how-do-i-specify-xslt-output-settings"></a><span data-ttu-id="e119d-104">XSLT 出力の設定を指定する方法を教えてください。</span><span class="sxs-lookup"><span data-stu-id="e119d-104">How do I specify XSLT output settings?</span></span>  
 <span data-ttu-id="e119d-105">BizTalk マッパーで、XML 宣言を含めるかどうかを指定し、出力インスタンス データで使用するエンコードを制御できます。</span><span class="sxs-lookup"><span data-stu-id="e119d-105">You can use the BizTalk Mapper to include or omit XML declarations, and control the encoding used for output instance data.</span></span>  
  
#### <a name="include-or-exclude-an-xml-declaration"></a><span data-ttu-id="e119d-106">XML 宣言のエクスクルードまたはインクルード</span><span class="sxs-lookup"><span data-stu-id="e119d-106">Include or exclude an XML declaration</span></span>  
  
1.  <span data-ttu-id="e119d-107">グリッド ビューで、マッパー グリッドをクリックします。</span><span class="sxs-lookup"><span data-stu-id="e119d-107">In the Grid view, click the mapper grid.</span></span> <span data-ttu-id="e119d-108">**プロパティ**ウィンドウにグリッドのプロパティが表示されます。</span><span class="sxs-lookup"><span data-stu-id="e119d-108">The **Properties** window displays the grid properties.</span></span>  
  
2.  <span data-ttu-id="e119d-109">ドロップダウン リストで、 **XML 宣言の省略**プロパティを選択**[はい]** XML 宣言を省略するか選択**いいえ**XML 宣言を省略するされません。</span><span class="sxs-lookup"><span data-stu-id="e119d-109">In the drop-down list for the **Omit XML Declaration** property, select **Yes** to omit an XML declaration, or select **No** not to omit an XML declaration.</span></span>  
  
#### <a name="set-encoding-for-output-instance-data"></a><span data-ttu-id="e119d-110">出力インスタンス データのエンコードを設定します。</span><span class="sxs-lookup"><span data-stu-id="e119d-110">Set encoding for output instance data</span></span>  
  
1.  <span data-ttu-id="e119d-111">グリッド ビューで、マッパー グリッドをクリックします。</span><span class="sxs-lookup"><span data-stu-id="e119d-111">In the Grid view, click the mapper grid.</span></span> <span data-ttu-id="e119d-112">**プロパティ**ウィンドウにグリッドのプロパティが表示されます。</span><span class="sxs-lookup"><span data-stu-id="e119d-112">The **Properties** window displays the grid properties.</span></span>  
  
2.  <span data-ttu-id="e119d-113">ドロップダウン リストで、 **XSLT エンコード**出力インスタンス データに使用するプロパティ、文字セットを選択します。</span><span class="sxs-lookup"><span data-stu-id="e119d-113">In the drop-down list for the **XSLT Encoding** property, select the character set you want to use for the output instance data.</span></span>  
  
## <a name="how-do-i-create-multipart-mappings"></a><span data-ttu-id="e119d-114">マルチパート マッピングを作成するにはどうすればよいですか。</span><span class="sxs-lookup"><span data-stu-id="e119d-114">How do I create multipart mappings?</span></span>  
 <span data-ttu-id="e119d-115">一緒に使用する複数のマップがある場合は、それらを使用して、オーケストレーションに結合する必要があります、**変換**図形を一緒にそれらをテストします。</span><span class="sxs-lookup"><span data-stu-id="e119d-115">If you have multiple maps that are used together, you will need to combine them in an orchestration by using the **Transform** shape to test them together.</span></span> <span data-ttu-id="e119d-116">BizTalk マッパーで一度にテストできるのは 1 つのマップだけです。</span><span class="sxs-lookup"><span data-stu-id="e119d-116">The BizTalk Mapper can test only one map at a time.</span></span>  
  
## <a name="why-isnt-my-database-functoid-working"></a><span data-ttu-id="e119d-117">データベース Functoid が動作しないのはなぜですか。</span><span class="sxs-lookup"><span data-stu-id="e119d-117">Why isn't my database functoid working?</span></span>  
 <span data-ttu-id="e119d-118">データベース functoid**データベース検索**と**値抽出**は、エラー情報を直接返さない情報をキャプチャするを指定して、代わりに、**エラーを返す** functoid マップで使用します。</span><span class="sxs-lookup"><span data-stu-id="e119d-118">The database functoids **Database Lookup** and **Value Extractor** do not directly return error information; rather, they capture the information and supply it to the **Error Return** functoid for use by your map.</span></span> <span data-ttu-id="e119d-119">使用することができます、**エラーを返す**functoid は、次のシナリオと同様に、エラー検出のため。</span><span class="sxs-lookup"><span data-stu-id="e119d-119">You can use the **Error Return** functoid for error detection as in the following scenarios:</span></span>  
  
-   <span data-ttu-id="e119d-120">マップが持っている場合、**データベース検索**または**値抽出**functoid が期待どおりに動作していないこと。</span><span class="sxs-lookup"><span data-stu-id="e119d-120">When your map has a **Database Lookup** or **Value Extractor** functoid that is not behaving as expected.</span></span> <span data-ttu-id="e119d-121">エラー メッセージを表示するには、この Functoid を出力スキーマのフィールドに一時的にマップしてください。</span><span class="sxs-lookup"><span data-stu-id="e119d-121">To see the error message, temporarily map the functoid to a field in the output schema.</span></span>  
  
-   <span data-ttu-id="e119d-122">データベース操作が失敗したときに、アプリケーションで別のメッセージ内容が要求された場合。</span><span class="sxs-lookup"><span data-stu-id="e119d-122">If your application expects different message content when database operations fail.</span></span> <span data-ttu-id="e119d-123">使用することができます、**エラーを返す**functoid をエラーを検出し、ダウン ストリーム アプリケーションが適切な方法で対処できるように、エラー メッセージを代替構造にマップします。</span><span class="sxs-lookup"><span data-stu-id="e119d-123">You can use the **Error Return** functoid to detect an error and map the error message to an alternate structure so that downstream applications can react in a controlled manner.</span></span>  
  
 <span data-ttu-id="e119d-124">実行時にのみが検出されたエラーを回避することを確認する最初のパラメーター、**エラーを返す**functoid の出力は、**データベース検索**functoid とその他の functoid に出力できません、データベースのカテゴリ。</span><span class="sxs-lookup"><span data-stu-id="e119d-124">To avoid errors that are detected only at run time, make sure that the first parameter to the **Error Return** functoid is the output of a **Database Lookup** functoid and not the output of any other functoid in the Database category.</span></span>  
  
 <span data-ttu-id="e119d-125">使用しての詳細については、**エラーを返す**functoid (サンプルを含む) を参照してください、 **Functoid リファレンス**[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]です。</span><span class="sxs-lookup"><span data-stu-id="e119d-125">For more information about using the **Error Return** functoid (including a sample), see the **Functoid Reference** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].</span></span>
  
## <a name="why-is-my-map-failing-when-calling-my-custom-functoid"></a><span data-ttu-id="e119d-126">カスタム Functoid を呼び出すとマップで障害が発生するのはなぜですか。</span><span class="sxs-lookup"><span data-stu-id="e119d-126">Why is my map failing when calling my custom functoid?</span></span>  
 <span data-ttu-id="e119d-127">マップでカスタム Functoid を呼び出せるようにするには、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] コンピューターのグローバル アセンブリ キャッシュ (GAC) にそれらのカスタム Functoid をインストールしておく必要があります。</span><span class="sxs-lookup"><span data-stu-id="e119d-127">Custom functoids must be installed into the global assembly cache (GAC) on the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] computer before they can be invoked by a map.</span></span> <span data-ttu-id="e119d-128">カスタム Functoid を含むアセンブリが署名されており、GAC に配置されていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="e119d-128">Verify that the assembly containing your custom functoid has been signed and placed into the GAC.</span></span> <span data-ttu-id="e119d-129">また、アセンブリを "%BTSINSTALLPATH%\Developer Tools\Mapper Extensions" フォルダーにコピーします。</span><span class="sxs-lookup"><span data-stu-id="e119d-129">Also, copy the assembly into the folder “%BTSINSTALLPATH%\Developer Tools\Mapper Extensions”.</span></span>  
  
 <span data-ttu-id="e119d-130">アセンブリを GAC にインストールの詳細については、次を参照してください。 [GAC にアセンブリのインストール](../core/assembly-installation-in-the-gac.md)です。</span><span class="sxs-lookup"><span data-stu-id="e119d-130">For more information about installing assemblies to the GAC, see [Assembly Installation in the GAC](../core/assembly-installation-in-the-gac.md).</span></span> <span data-ttu-id="e119d-131">GAC にインストールされたアセンブリを表示するには、[!INCLUDE[btsWinNoVersion](../includes/btswinnoversion-md.md)] のインストール ディレクトリの Assembly ディレクトリに移動します。</span><span class="sxs-lookup"><span data-stu-id="e119d-131">To view assemblies installed in the GAC, navigate to the Assembly directory of your [!INCLUDE[btsWinNoVersion](../includes/btswinnoversion-md.md)] installation directory.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e119d-132">参照</span><span class="sxs-lookup"><span data-stu-id="e119d-132">See Also</span></span>  
 [<span data-ttu-id="e119d-133">マップのトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="e119d-133">Troubleshooting Maps</span></span>](../core/troubleshooting-maps.md)