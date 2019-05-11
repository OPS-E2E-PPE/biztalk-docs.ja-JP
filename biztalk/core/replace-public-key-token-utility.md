---
title: パブリック キー トークンのユーティリティを置き換える |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Replace Public Key Token Utility
- utilities, Replace Public Key Token Utility
- public key token
ms.assetid: ed8673b9-af06-4bd7-b8b7-7371e4dd0fed
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5754f9ee853f1501d247f1236ca89d158b3788c0
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65397906"
---
# <a name="replace-public-key-token-utility"></a><span data-ttu-id="74b79-102">パブリック キー トークンのユーティリティを置き換える</span><span class="sxs-lookup"><span data-stu-id="74b79-102">Replace Public Key Token Utility</span></span>
<span data-ttu-id="74b79-103">このユーティリティにいずれかの公開キー トークンまたは変数でファイルを厳密な名前のアセンブリ キー (.snk) ファイルから抽出した公開キー トークンに置き換えて使用できます。</span><span class="sxs-lookup"><span data-stu-id="74b79-103">This utility can be used to replace either a public key token or variable in a file with a public key token derived from a strong name assembly key (.snk) file.</span></span>  
  
 <span data-ttu-id="74b79-104">開発者が使用するスクリプトを記述する場合、このユーティリティが便利なあります、 [BTSTask コマンド ライン リファレンス](../core/btstask-command-line-reference.md)アセンブリを展開します。</span><span class="sxs-lookup"><span data-stu-id="74b79-104">This utility might be useful when a developer is writing a script that uses the [BTSTask Command-Line Reference](../core/btstask-command-line-reference.md) to deploy an assembly.</span></span> <span data-ttu-id="74b79-105">展開を成功させるには、その公開キー トークンを含む、アセンブリの完全修飾名を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="74b79-105">For the deployment to succeed, the fully qualified name of the assembly must be provided, which includes its public key token.</span></span> <span data-ttu-id="74b79-106">アセンブリの公開キー トークンは、.snk ファイルから抽出し、ビルド時に、アセンブリに割り当てられています。</span><span class="sxs-lookup"><span data-stu-id="74b79-106">The public key token for an assembly is extracted from an .snk file and assigned to the assembly when it is built.</span></span> <span data-ttu-id="74b79-107">アセンブリは、新しい環境に展開は、前にただし、多くの場合、再構築されます別の公開キー トークンを使用します。</span><span class="sxs-lookup"><span data-stu-id="74b79-107">Before the assembly is deployed into a new environment, however, it is often rebuilt using a different public key token.</span></span> <span data-ttu-id="74b79-108">結果として、開発者では、どのような公開キー トークンは、配置スクリプトの実行時にアセンブリに使用されますが知らないです。</span><span class="sxs-lookup"><span data-stu-id="74b79-108">As a result, the developer may not know what public key token will be used for the assembly when the deployment script is run.</span></span>  
  
 <span data-ttu-id="74b79-109">このような状況に対処する公開キー トークンの置換ユーティリティを使用できる 2 つの方法はあります。</span><span class="sxs-lookup"><span data-stu-id="74b79-109">There are two ways that you can use the Replace Public Key Token utility to address this situation:</span></span>  
  
-   <span data-ttu-id="74b79-110">**シナリオ 1。**</span><span class="sxs-lookup"><span data-stu-id="74b79-110">**Scenario 1.**</span></span> <span data-ttu-id="74b79-111">配置スクリプトでは、開発者は公開キー トークンまたは公開キー トークンを表すプレース ホルダーのいずれかを使用できます。</span><span class="sxs-lookup"><span data-stu-id="74b79-111">In the deployment script, the developer can use either a public key token or a placeholder representing the public key token.</span></span> <span data-ttu-id="74b79-112">スクリプトを実行する前に、ユーザーは、公開キー トークンまたはスクリプト ファイル内のプレース ホルダーを送信先の環境のアセンブリを構築するために使用された .snk ファイルから抽出した公開キー トークンで代用する公開キー トークンの置換ユーティリティを実行できます。</span><span class="sxs-lookup"><span data-stu-id="74b79-112">Before running the script, a user can run the Replace Public Key Token utility to substitute the public key token or placeholder in the script file with the public key token extracted from the .snk file that was used to build the assembly for the destination environment.</span></span>  
  
-   <span data-ttu-id="74b79-113">**シナリオ 2。**</span><span class="sxs-lookup"><span data-stu-id="74b79-113">**Scenario 2.**</span></span> <span data-ttu-id="74b79-114">開発者は、自動的に次のように新しい公開キー トークンを置換するスクリプトを構成できます。スクリプトの先頭には、公開キー トークンの置換ユーティリティを起動し、公開キー トークンを含む .snk ファイルをポイントします。</span><span class="sxs-lookup"><span data-stu-id="74b79-114">The developer can configure the script to automatically substitute the new public key token, as follows: At the start of the script, invoke the Replace Public Key Token utility and point it to a .snk file that contains the public key token.</span></span> <span data-ttu-id="74b79-115">スクリプト内では、環境変数 %newtoken% を使用して、公開キー トークンを表します。</span><span class="sxs-lookup"><span data-stu-id="74b79-115">Within the script, use the environment variable %NEWTOKEN% to represent the public key token.</span></span> <span data-ttu-id="74b79-116">スクリプトを実行すると、このユーティリティは、.snk ファイルから公開キー トークンの値を抽出を環境変数 %newtoken% に設定。</span><span class="sxs-lookup"><span data-stu-id="74b79-116">When the script runs, the utility extracts the value of the public key token from the .snk file and sets it into an environment variable %NEWTOKEN%.</span></span> <span data-ttu-id="74b79-117">スクリプトの実行時に %newtoken% の各インスタンスに置き換えられる、指定された .snk ファイルから公開キー トークン。</span><span class="sxs-lookup"><span data-stu-id="74b79-117">When the script runs, each instance of %NEWTOKEN% will be with substituted with the public key token from the specified .snk file.</span></span> <span data-ttu-id="74b79-118">例 :</span><span class="sxs-lookup"><span data-stu-id="74b79-118">For example:</span></span>  
  
    ```  
    ReplacePKT.bat key.snk  
    ...  
    ...  
    gacutil /u Assembly, ... PublicKey=%NEWTOKEN% ...  
    ```  
  
## <a name="location-in-sdk"></a><span data-ttu-id="74b79-119">SDK でのパス</span><span class="sxs-lookup"><span data-stu-id="74b79-119">Location in SDK</span></span>  
 <span data-ttu-id="74b79-120">公開キー トークンの置換ユーティリティはあります。</span><span class="sxs-lookup"><span data-stu-id="74b79-120">The Replace Public Key Token utility is located in:</span></span>  
  
 [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]<span data-ttu-id="74b79-121">SDK\Utilities\ReplacePublicKeyToken\\します。</span><span class="sxs-lookup"><span data-stu-id="74b79-121">SDK\Utilities\ReplacePublicKeyToken\\.</span></span>  
  
 <span data-ttu-id="74b79-122">公開キー トークンの置換ユーティリティには、3 つのファイルが構成されています。</span><span class="sxs-lookup"><span data-stu-id="74b79-122">The Replace Public Key Token utility comprises three files:</span></span>  
  
-   <span data-ttu-id="74b79-123">ReplacePKT.bat</span><span class="sxs-lookup"><span data-stu-id="74b79-123">ReplacePKT.bat</span></span>  
  
-   <span data-ttu-id="74b79-124">ReplacePKT.vbs</span><span class="sxs-lookup"><span data-stu-id="74b79-124">ReplacePKT.vbs</span></span>  
  
-   <span data-ttu-id="74b79-125">ReplacePKT.wsf</span><span class="sxs-lookup"><span data-stu-id="74b79-125">ReplacePKT.wsf</span></span>  
  
## <a name="procedures"></a><span data-ttu-id="74b79-126">手順</span><span class="sxs-lookup"><span data-stu-id="74b79-126">Procedures</span></span>  
 <span data-ttu-id="74b79-127">シナリオ 1」の説明に従って、.snk ファイルから抽出されたパブリック キー トークンを使用して公開キー トークンまたはプレース ホルダー ファイル内のすべてのインスタンスを置換するのにには、次の手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="74b79-127">Use the following procedure to replace all instances of a public key token or a placeholder in a file with a public key token extracted from an .snk file, as described in Scenario 1.</span></span>  
  
#### <a name="to-replace-instances-of-a-public-key-token-or-a-placeholder-in-a-file"></a><span data-ttu-id="74b79-128">公開キー トークンまたはファイル内のプレース ホルダーのインスタンスを置換するには</span><span class="sxs-lookup"><span data-stu-id="74b79-128">To replace instances of a public key token or a placeholder in a file</span></span>  
  
1. <span data-ttu-id="74b79-129">3 つのパブリック キー トークンの置換ユーティリティ ファイル (ReplacePKT.bat、ReplacePKT.vbs、および ReplacePKT.wsf)、スクリプト ファイル、および .snk ファイルがローカル コンピューターから使用可能なすべてを確認します。</span><span class="sxs-lookup"><span data-stu-id="74b79-129">Make sure that the three Replace Public Key Token utility files (ReplacePKT.bat, ReplacePKT.vbs, ReplacePKT.wsf), the script file, and the .snk file are all available from the local computer.</span></span>  
  
2. <span data-ttu-id="74b79-130">コマンド ウィンドウでは、公開キーの置換ユーティリティのファイルを含むフォルダーにディレクトリを変更します。</span><span class="sxs-lookup"><span data-stu-id="74b79-130">In a command window, change the directory to the folder containing the Replace Public Key utility files.</span></span>  
  
3. <span data-ttu-id="74b79-131">コマンド プロンプトから次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="74b79-131">From a command prompt, run the following command:</span></span>  
  
4. <span data-ttu-id="74b79-132">**ReplacePKT \<**  *.snk ファイル* **\> \<** *古い公開キー トークン* **\>\<** *ファイルを置き換える* **\>**</span><span class="sxs-lookup"><span data-stu-id="74b79-132">**ReplacePKT \<** *.snk file* **\> \<** *old public key token* **\> \<** *file to replace* **\>**</span></span>  
  
   |<span data-ttu-id="74b79-133">オプション</span><span class="sxs-lookup"><span data-stu-id="74b79-133">Option</span></span>|<span data-ttu-id="74b79-134">説明</span><span class="sxs-lookup"><span data-stu-id="74b79-134">Description</span></span>|  
   |------------|-----------------|  
   |<span data-ttu-id="74b79-135">**\<** *.snk file* **\>**</span><span class="sxs-lookup"><span data-stu-id="74b79-135">**\<** *.snk file* **\>**</span></span>|<span data-ttu-id="74b79-136">既存の公開キー トークンまたはプレース ホルダーを使用する公開キー トークンを含む .snk ファイルの完全なパスに置き換えてください。</span><span class="sxs-lookup"><span data-stu-id="74b79-136">Full path of the .snk file containing the public key token that you want substitute for the existing public key token or placeholder.</span></span>|  
   |<span data-ttu-id="74b79-137">**\<** *古い公開キー トークン* **\>**</span><span class="sxs-lookup"><span data-stu-id="74b79-137">**\<** *old public key token* **\>**</span></span>|<span data-ttu-id="74b79-138">公開キー トークンまたはプレース ホルダーを置き換えます。</span><span class="sxs-lookup"><span data-stu-id="74b79-138">Public key token or placeholder that you want to replace.</span></span>|  
   |<span data-ttu-id="74b79-139">**\<** *ファイルを置き換える* **\>**</span><span class="sxs-lookup"><span data-stu-id="74b79-139">**\<** *file to replace* **\>**</span></span>|<span data-ttu-id="74b79-140">公開キー トークンまたはプレース ホルダーを置換するファイルの完全パス。</span><span class="sxs-lookup"><span data-stu-id="74b79-140">Full path of the file in which you want to replace the public key token or placeholder.</span></span>|  
  
    <span data-ttu-id="74b79-141">例:</span><span class="sxs-lookup"><span data-stu-id="74b79-141">Example:</span></span>  
  
    <span data-ttu-id="74b79-142">**ReplacePKT.bat C:\Tokens\MyToken.snk 12ab3456cd789e12 C:\Scripts\MyScript.vbs**</span><span class="sxs-lookup"><span data-stu-id="74b79-142">**ReplacePKT.bat C:\Tokens\MyToken.snk 12ab3456cd789e12 C:\Scripts\MyScript.vbs**</span></span>  
  
   <span data-ttu-id="74b79-143">シナリオ 2」の説明に従って、.snk ファイルから抽出した公開キー トークンを使用するスクリプトで環境変数を自動的に設定するのにには、次の手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="74b79-143">Use the following procedure to automatically set an environment variable in a script that uses a public key token derived from an .snk file, as described in Scenario 2.</span></span>  
  
#### <a name="to-set-an-environment-variable-that-uses-a-public-key-token"></a><span data-ttu-id="74b79-144">公開キー トークンを使用する環境変数を設定するには</span><span class="sxs-lookup"><span data-stu-id="74b79-144">To set an environment variable that uses a public key token</span></span>  
  
1.  <span data-ttu-id="74b79-145">スクリプト ファイルの先頭には、次のコード行を追加します。</span><span class="sxs-lookup"><span data-stu-id="74b79-145">At the beginning of your script file, add the following line of code:</span></span>  
  
    ```  
    ReplacePKT <filename>.snk  
    ```  
  
     <span data-ttu-id="74b79-146">場所\< *filename* \>公開キー トークンを取得する .snk ファイルの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="74b79-146">Where \<*filename*\> is the name of the .snk file from which to derive the public key token.</span></span>  
  
    ```  
    Example: ReplacePKT.bat MyToken.snk  
    ```  
  
2.  <span data-ttu-id="74b79-147">スクリプト ファイルには、`%NEWTOKEN%`公開キー トークンを表すため。</span><span class="sxs-lookup"><span data-stu-id="74b79-147">In your script file, use `%NEWTOKEN%` to represent the public key token.</span></span>  
  
     <span data-ttu-id="74b79-148">例:</span><span class="sxs-lookup"><span data-stu-id="74b79-148">Example:</span></span>  
  
    ```  
    PublicKey=%NEWTOKEN%  
    ```  
  
3.  <span data-ttu-id="74b79-149">スクリプト ファイルをユーザーに提供する場合に、(ReplacePKT.bat、ReplacePKT.vbs、および ReplacePKT.wsf)、公開キー トークンの置換ユーティリティを構成する 3 つのファイルが含まれます。</span><span class="sxs-lookup"><span data-stu-id="74b79-149">When you deliver your script file to your users, include the three files that comprise the Replace Public Key Token utility (ReplacePKT.bat, ReplacePKT.vbs, ReplacePKT.wsf).</span></span> <span data-ttu-id="74b79-150">コピーしてください、スクリプトのユーザーのすべてのファイル、ファイル システム上の同じフォルダーにスクリプトを実行する前にします。</span><span class="sxs-lookup"><span data-stu-id="74b79-150">Make sure that users of your script copy all of the files to the same folder on the file system before running your script.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="74b79-151">参照</span><span class="sxs-lookup"><span data-stu-id="74b79-151">See Also</span></span>  
 [<span data-ttu-id="74b79-152">SDK のユーティリティ</span><span class="sxs-lookup"><span data-stu-id="74b79-152">Utilities in the SDK</span></span>](../core/utilities-in-the-sdk.md)