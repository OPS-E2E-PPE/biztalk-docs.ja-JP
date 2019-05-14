---
title: BAM 定義を展開する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- deploying, definitions [BAM]
- managing [BAM definitions], deploying definitions
- definitions [BAM], deploying
- Deploy-All command [BAM]
ms.assetid: 02b8888c-6f6c-45dd-8445-6e507a02f5f0
caps.latest.revision: 21
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 58d2711ee5bdf9e280ad32610031d5720d8d2c36
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65385277"
---
# <a name="how-to-deploy-bam-definitions"></a><span data-ttu-id="cf1fc-102">BAM 定義を展開する方法</span><span class="sxs-lookup"><span data-stu-id="cf1fc-102">How to Deploy BAM Definitions</span></span>
<span data-ttu-id="cf1fc-103">管理者を使用して、**展開すべて**Excel ブックまたは XML 定義ファイルから BAM 定義を展開する BAM 管理ユーティリティのコマンドは、ブックからエクスポートします。</span><span class="sxs-lookup"><span data-stu-id="cf1fc-103">Administrators use the **deploy-all** BAM Management utility command to deploy a BAM definition from the Excel workbook or the XML definitions file exported from the workbook.</span></span> <span data-ttu-id="cf1fc-104">完全なインストールを実行するときに[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]、構成ウィザードでは、BAM 構成 XML は、自動的に構成されます。</span><span class="sxs-lookup"><span data-stu-id="cf1fc-104">When you perform a complete installation of [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], the Configuration Wizard automatically configures the BAM Configuration XML.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="cf1fc-105">複数のユーザーは、Excel 用 BAM アドインで作業は場合、は、同じバージョンの Microsoft Data Access Components (MDAC) があることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="cf1fc-105">If multiple users are working with the BAM Add-In for Excel, we recommend that they have the same version of Microsoft Data Access Components (MDAC).</span></span> <span data-ttu-id="cf1fc-106">それ以外の場合、互換性の問題が発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="cf1fc-106">Otherwise, compatibility issues may arise.</span></span> <span data-ttu-id="cf1fc-107">具体的には、新しいバージョンの MDAC を使用しているコンピューターで、テンプレートを作成し、古いバージョンの MDAC を使用しているコンピューターでそれを開こうとする場合、コンパイラ エラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="cf1fc-107">Specifically, if you create a template on a computer with a newer version of MDAC and then attempt to open it on a computer with an older version of MDAC, a compiler error will occur.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="cf1fc-108">データ ディメンション (場所など) ごとの 1 つだけのデータ項目 (たとえば、City) を使用することができます。</span><span class="sxs-lookup"><span data-stu-id="cf1fc-108">You can use only one data item (for example, City) per data dimension (for example, Location).</span></span> <span data-ttu-id="cf1fc-109">リージョンなどの別のデータ ディメンションでは、市区町村をもう一度使用できません。</span><span class="sxs-lookup"><span data-stu-id="cf1fc-109">You cannot use City again in another data dimension, such as Region.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="cf1fc-110">これらを展開する前に、BAM Excel ブック (.xls) のセキュリティを確認することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="cf1fc-110">We recommend that you verify the security of BAM Excel workbooks (.xls) before you deploy them.</span></span> <span data-ttu-id="cf1fc-111">管理コンピューターに Excel を使用すると、BAM Excel ブックのセキュリティを確認できます。</span><span class="sxs-lookup"><span data-stu-id="cf1fc-111">You use Excel on the administration computer to verify the security of BAM Excel workbooks.</span></span> <span data-ttu-id="cf1fc-112">ブックを展開する前に開くし、マクロのセキュリティは、高に設定され、警告がないことを確認します。</span><span class="sxs-lookup"><span data-stu-id="cf1fc-112">Before you deploy a workbook, open it and ensure the macro security is set to high, and that there are no warnings.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="cf1fc-113">BAM データベースで、"bam _\<.\>"すべての SQL エンティティの名前付け規則は予約されています (テーブル、インデックス、ストアド プロシージャ、ロールなど.)。*しない*この名前付け規則を使用して、SQL エンティティを作成する。 このような使用状況は、未定義の動作を、可能性があります。</span><span class="sxs-lookup"><span data-stu-id="cf1fc-113">In BAM databases, the “BAM_\<...\>” naming convention is reserved for all SQL entities (tables, indexes, stored procedures, roles, etc...). *Do not* use this naming convention to create any SQL entities; such a usage might result in an undefined behavior.</span></span>  
  
 <span data-ttu-id="cf1fc-114">BAM 定義 XML ファイルを展開する前に、このファイルを作成するために使用するロケールをデプロイしているコンピューターのロケールと一致していることを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="cf1fc-114">Before you can deploy a BAM definition XML file, you must ensure that the locale used to create this file matches the locale of the computer on which you are deploying it.</span></span> <span data-ttu-id="cf1fc-115">たとえば、日本語版の Microsoft Windows を実行しているコンピューター上のファイルを作成する場合でファイルを展開するコンピューターは日本語のロケールを設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="cf1fc-115">For example, if you create the file on a computer running a Japanese version of Microsoft Windows, the computer you deploy the file on must be set to the Japanese locale.</span></span> <span data-ttu-id="cf1fc-116">ファイルとコンピューターの設定が一致しない場合は、使用して適切なロケールに、BAM 管理ユーティリティを実行するコンピューターを切り替える必要があり、ユーティリティを実行する前に再起動する必要があります。</span><span class="sxs-lookup"><span data-stu-id="cf1fc-116">If the file and the computer settings do not match, you must switch the computer you use to run the BAM Management utility to the correct locale and you must restart it before running the utility.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="cf1fc-117">すべての言語を使用して、同じコード ページ、または 2 つだけの言語が含まれます、1 つは英語でない限り、BAM 定義 XML ファイルは複数の言語でテキストを含めることはできません。</span><span class="sxs-lookup"><span data-stu-id="cf1fc-117">The BAM definition XML file cannot contain text in multiple languages unless the languages all use the same codepage, or only two languages are included and one of them is English.</span></span>  
  
 <span data-ttu-id="cf1fc-118">コンピューターのロケール設定を変更する方法の詳細については、オペレーティング システムのヘルプを参照してください。</span><span class="sxs-lookup"><span data-stu-id="cf1fc-118">For information about changing locale settings on your computer, see the Help for your operating system.</span></span>  
  
### <a name="to-deploy-a-bam-definition"></a><span data-ttu-id="cf1fc-119">BAM 定義を展開するには</span><span class="sxs-lookup"><span data-stu-id="cf1fc-119">To deploy a BAM definition</span></span>  
  
1.  <span data-ttu-id="cf1fc-120">次のように、コマンド プロンプトを開きます。をクリックして**開始**、 をクリックして**実行**、型**cmd**、順にクリックします**OK**。</span><span class="sxs-lookup"><span data-stu-id="cf1fc-120">Open a command prompt as follows: Click **Start**, click **Run**, type **cmd**, and then click **OK**.</span></span>  
  
2.  <span data-ttu-id="cf1fc-121">入力して、追跡フォルダーに移動します**C:\Program files \microsoft BizTalk Server\<バージョン\>\Tracking**コマンド プロンプトでします。</span><span class="sxs-lookup"><span data-stu-id="cf1fc-121">Navigate to the tracking folder by typing **C:\Program Files\Microsoft BizTalk Server \<version\>\Tracking** at the command prompt.</span></span> <span data-ttu-id="cf1fc-122">**Enter**キーを押します。</span><span class="sxs-lookup"><span data-stu-id="cf1fc-122">Press **ENTER**.</span></span>  
  
3.  <span data-ttu-id="cf1fc-123">型**bm 展開すべて-definitionfile:\<BAM 定義ファイル\>** します。</span><span class="sxs-lookup"><span data-stu-id="cf1fc-123">Type **bm deploy-all -DefinitionFile:\<BAM definition file\>**.</span></span>  
  
4.  <span data-ttu-id="cf1fc-124">**Enter**キーを押します。</span><span class="sxs-lookup"><span data-stu-id="cf1fc-124">Press **ENTER**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cf1fc-125">参照</span><span class="sxs-lookup"><span data-stu-id="cf1fc-125">See Also</span></span>  
 <span data-ttu-id="cf1fc-126">[BAM 動的インフラストラクチャの管理](../core/managing-the-bam-dynamic-infrastructure.md) </span><span class="sxs-lookup"><span data-stu-id="cf1fc-126">[Managing the BAM Dynamic Infrastructure](../core/managing-the-bam-dynamic-infrastructure.md) </span></span>  
 <span data-ttu-id="cf1fc-127">[BAM 管理ユーティリティ](../core/bam-management-utility.md) </span><span class="sxs-lookup"><span data-stu-id="cf1fc-127">[BAM Management Utility](../core/bam-management-utility.md) </span></span>  
 [<span data-ttu-id="cf1fc-128">BAM のセキュリティに関する推奨事項</span><span class="sxs-lookup"><span data-stu-id="cf1fc-128">BAM Security Recommendations</span></span>](../core/bam-security-recommendations.md)