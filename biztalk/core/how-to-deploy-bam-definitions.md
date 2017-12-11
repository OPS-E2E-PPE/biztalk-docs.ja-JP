---
title: "BAM 定義を展開する方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- deploying, definitions [BAM]
- managing [BAM definitions], deploying definitions
- definitions [BAM], deploying
- Deploy-All command [BAM]
ms.assetid: 02b8888c-6f6c-45dd-8445-6e507a02f5f0
caps.latest.revision: "21"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 094a37d90db41e505adeaec3a31ece9128785e04
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
---
# <a name="how-to-deploy-bam-definitions"></a><span data-ttu-id="4bace-102">BAM 定義を展開する方法</span><span class="sxs-lookup"><span data-stu-id="4bace-102">How to Deploy BAM Definitions</span></span>
<span data-ttu-id="4bace-103">管理者を使用して、**展開すべて**Excel ブックまたは XML 定義ファイルから BAM 定義を展開する BAM 管理ユーティリティのコマンドは、ブックからエクスポートします。</span><span class="sxs-lookup"><span data-stu-id="4bace-103">Administrators use the **deploy-all** BAM Management utility command to deploy a BAM definition from the Excel workbook or the XML definitions file exported from the workbook.</span></span> <span data-ttu-id="4bace-104">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] の完全インストールを実行すると、構成ウィザードで BAM 構成 XML が自動的に構成されます。</span><span class="sxs-lookup"><span data-stu-id="4bace-104">When you perform a complete installation of [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], the Configuration Wizard automatically configures the BAM Configuration XML.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="4bace-105">複数のユーザーは、Excel 用 BAM アドインで作業は場合、は、同じバージョンの Microsoft Data Access Components (MDAC) があることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="4bace-105">If multiple users are working with the BAM Add-In for Excel, we recommend that they have the same version of Microsoft Data Access Components (MDAC).</span></span> <span data-ttu-id="4bace-106">同じバージョンを使用しないと、互換性の問題が発生する場合があります。</span><span class="sxs-lookup"><span data-stu-id="4bace-106">Otherwise, compatibility issues may arise.</span></span> <span data-ttu-id="4bace-107">具体的には、新しいバージョンの MDAC を使用しているコンピューター上でテンプレートを作成した後、古いバージョンの MDAC を使用しているコンピューターでそのテンプレートを開くと、コンパイラ エラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="4bace-107">Specifically, if you create a template on a computer with a newer version of MDAC and then attempt to open it on a computer with an older version of MDAC, a compiler error will occur.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="4bace-108">各データ ディメンション (例、Location) では、データ項目 (例、City) を 1 つだけ使用できます。</span><span class="sxs-lookup"><span data-stu-id="4bace-108">You can use only one data item (for example, City) per data dimension (for example, Location).</span></span> <span data-ttu-id="4bace-109">City を Region など別のデータ ディメンションで再度使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="4bace-109">You cannot use City again in another data dimension, such as Region.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="4bace-110">BAM Excel ブック (.xls) のセキュリティを確認してから展開することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="4bace-110">We recommend that you verify the security of BAM Excel workbooks (.xls) before you deploy them.</span></span> <span data-ttu-id="4bace-111">BAM Excel ブックのセキュリティを確認するには、管理用コンピューターで Excel を使用します。</span><span class="sxs-lookup"><span data-stu-id="4bace-111">You use Excel on the administration computer to verify the security of BAM Excel workbooks.</span></span> <span data-ttu-id="4bace-112">ブックを展開する前に開き、マクロのセキュリティが [高] に設定されているし、警告がないことを確認します。</span><span class="sxs-lookup"><span data-stu-id="4bace-112">Before you deploy a workbook, open it and ensure the macro security is set to high, and that there are no warnings.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="4bace-113">BAM データベースで、"bam _\<.\>"SQL のすべてのエンティティの名前付け規則は予約されています (テーブル、インデックス、ストアド プロシージャ、ロールなど.) です。*そうしない*この名前付け規則を使用して、SQL エンティティを作成する以外の場合は、このような使用法は動作が不安定になる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="4bace-113">In BAM databases, the “BAM_\<...\>” naming convention is reserved for all SQL entities (tables, indexes, stored procedures, roles, etc...). *Do not* use this naming convention to create any SQL entities; such a usage might result in an undefined behavior.</span></span>  
  
 <span data-ttu-id="4bace-114">BAM 定義 XML ファイルを展開する前に、このファイルの作成に使用したロケールが展開先のコンピューターのロケールに一致することを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4bace-114">Before you can deploy a BAM definition XML file, you must ensure that the locale used to create this file matches the locale of the computer on which you are deploying it.</span></span> <span data-ttu-id="4bace-115">たとえば、日本語版の Microsoft Windows を実行しているコンピューターでファイルを作成した場合は、そのファイルを展開するコンピューターのロケールを日本語に設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4bace-115">For example, if you create the file on a computer running a Japanese version of Microsoft Windows, the computer you deploy the file on must be set to the Japanese locale.</span></span> <span data-ttu-id="4bace-116">ファイルとコンピューターの設定が一致しない場合は、BAM 管理ユーティリティの実行に使用するコンピューターを適切なロケールに切り替え、ユーティリティを実行する前にコンピューターを再起動する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4bace-116">If the file and the computer settings do not match, you must switch the computer you use to run the BAM Management utility to the correct locale and you must restart it before running the utility.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="4bace-117">すべての言語で同じコード ページを使用している場合、または英語を含む 2 種類の言語だけを使用している場合を除いて、BAM 定義 XML ファイルに複数の言語のテキストを含めることはできません。</span><span class="sxs-lookup"><span data-stu-id="4bace-117">The BAM definition XML file cannot contain text in multiple languages unless the languages all use the same codepage, or only two languages are included and one of them is English.</span></span>  
  
 <span data-ttu-id="4bace-118">コンピューターのロケールの設定を変更する方法については、オペレーティング システムのヘルプを参照してください。</span><span class="sxs-lookup"><span data-stu-id="4bace-118">For information about changing locale settings on your computer, see the Help for your operating system.</span></span>  
  
### <a name="to-deploy-a-bam-definition"></a><span data-ttu-id="4bace-119">BAM 定義を展開するには</span><span class="sxs-lookup"><span data-stu-id="4bace-119">To deploy a BAM definition</span></span>  
  
1.  <span data-ttu-id="4bace-120">次のように、コマンド プロンプトを開きます: をクリックして**開始**、 をクリックして**実行**、型**cmd**、順にクリック**ok**です。</span><span class="sxs-lookup"><span data-stu-id="4bace-120">Open a command prompt as follows: Click **Start**, click **Run**, type **cmd**, and then click **OK**.</span></span>  
  
2.  <span data-ttu-id="4bace-121">」と入力して、追跡フォルダーに移動**C:\Program files \microsoft BizTalk Server\<バージョン\>\Tracking**コマンド プロンプトでします。</span><span class="sxs-lookup"><span data-stu-id="4bace-121">Navigate to the tracking folder by typing **C:\Program Files\Microsoft BizTalk Server \<version\>\Tracking** at the command prompt.</span></span> <span data-ttu-id="4bace-122">**Enter**キーを押します。</span><span class="sxs-lookup"><span data-stu-id="4bace-122">Press **ENTER**.</span></span>  
  
3.  <span data-ttu-id="4bace-123">型**bm 展開すべて-definitionfile:\<BAM 定義ファイル\>**です。</span><span class="sxs-lookup"><span data-stu-id="4bace-123">Type **bm deploy-all -DefinitionFile:\<BAM definition file\>**.</span></span>  
  
4.  <span data-ttu-id="4bace-124">**Enter**キーを押します。</span><span class="sxs-lookup"><span data-stu-id="4bace-124">Press **ENTER**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4bace-125">参照</span><span class="sxs-lookup"><span data-stu-id="4bace-125">See Also</span></span>  
 <span data-ttu-id="4bace-126">[BAM 動的インフラストラクチャの管理](../core/managing-the-bam-dynamic-infrastructure.md) </span><span class="sxs-lookup"><span data-stu-id="4bace-126">[Managing the BAM Dynamic Infrastructure](../core/managing-the-bam-dynamic-infrastructure.md) </span></span>  
 <span data-ttu-id="4bace-127">[BAM 管理ユーティリティ](../core/bam-management-utility.md) </span><span class="sxs-lookup"><span data-stu-id="4bace-127">[BAM Management Utility](../core/bam-management-utility.md) </span></span>  
 [<span data-ttu-id="4bace-128">BAM のセキュリティに関する推奨事項</span><span class="sxs-lookup"><span data-stu-id="4bace-128">BAM Security Recommendations</span></span>](../core/bam-security-recommendations.md)