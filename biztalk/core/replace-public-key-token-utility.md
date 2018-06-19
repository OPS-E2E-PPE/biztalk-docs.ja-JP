---
title: パブリック キー トークンのユーティリティを置き換える |Microsoft ドキュメント
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
ms.openlocfilehash: 344b25b83060143b339a6791ecae6f3ab7028055
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
ms.locfileid: "25972048"
---
# <a name="replace-public-key-token-utility"></a><span data-ttu-id="3bbd2-102">公開キー トークンの置換ユーティリティ</span><span class="sxs-lookup"><span data-stu-id="3bbd2-102">Replace Public Key Token Utility</span></span>
<span data-ttu-id="3bbd2-103">このユーティリティを使用すると、ファイル内の公開キー トークンまたは変数のいずれかを、厳密な名前のアセンブリ キー (.snk) ファイルから抽出した公開キー トークンに置き換えることができます。</span><span class="sxs-lookup"><span data-stu-id="3bbd2-103">This utility can be used to replace either a public key token or variable in a file with a public key token derived from a strong name assembly key (.snk) file.</span></span>  
  
 <span data-ttu-id="3bbd2-104">開発者が使用するスクリプトを記述する場合、このユーティリティが便利なあります、 [BTSTask コマンドライン リファレンス](../core/btstask-command-line-reference.md)アセンブリを展開します。</span><span class="sxs-lookup"><span data-stu-id="3bbd2-104">This utility might be useful when a developer is writing a script that uses the [BTSTask Command-Line Reference](../core/btstask-command-line-reference.md) to deploy an assembly.</span></span> <span data-ttu-id="3bbd2-105">展開を成功させるには、アセンブリの完全修飾名を指定する必要があります。この完全修飾名には、アセンブリの公開キー トークンが含まれます。</span><span class="sxs-lookup"><span data-stu-id="3bbd2-105">For the deployment to succeed, the fully qualified name of the assembly must be provided, which includes its public key token.</span></span> <span data-ttu-id="3bbd2-106">アセンブリの公開キー トークンは、.snk ファイルから抽出され、アセンブリの構築時に割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="3bbd2-106">The public key token for an assembly is extracted from an .snk file and assigned to the assembly when it is built.</span></span> <span data-ttu-id="3bbd2-107">ただし、アセンブリを新しい環境に展開する前に、別の公開キー トークンを使用してアセンブリを再構築することがしばしばあります。</span><span class="sxs-lookup"><span data-stu-id="3bbd2-107">Before the assembly is deployed into a new environment, however, it is often rebuilt using a different public key token.</span></span> <span data-ttu-id="3bbd2-108">その結果、展開スクリプトを実行する際に、アセンブリで使用される公開キー トークンを開発者が知らないという状況が生じます。</span><span class="sxs-lookup"><span data-stu-id="3bbd2-108">As a result, the developer may not know what public key token will be used for the assembly when the deployment script is run.</span></span>  
  
 <span data-ttu-id="3bbd2-109">公開キー トークンの置換ユーティリティを使用してこの状況に対処するには、次の 2 つの方法があります。</span><span class="sxs-lookup"><span data-stu-id="3bbd2-109">There are two ways that you can use the Replace Public Key Token utility to address this situation:</span></span>  
  
-   <span data-ttu-id="3bbd2-110">**シナリオ 1 です。**</span><span class="sxs-lookup"><span data-stu-id="3bbd2-110">**Scenario 1.**</span></span> <span data-ttu-id="3bbd2-111">開発者は、公開キー トークンまたはそれを表すプレースホルダーのいずれかを展開スクリプト内で使用できます。</span><span class="sxs-lookup"><span data-stu-id="3bbd2-111">In the deployment script, the developer can use either a public key token or a placeholder representing the public key token.</span></span> <span data-ttu-id="3bbd2-112">ユーザーは、スクリプトを実行する前に、公開キー トークンの置換ユーティリティを使用して、スクリプト ファイル内の公開キー トークンまたはプレースホルダーを、.snk ファイル (展開先の環境に合わせてアセンブリを構築する際に使用されたもの) から抽出した公開キー トークンに置き換えることができます。</span><span class="sxs-lookup"><span data-stu-id="3bbd2-112">Before running the script, a user can run the Replace Public Key Token utility to substitute the public key token or placeholder in the script file with the public key token extracted from the .snk file that was used to build the assembly for the destination environment.</span></span>  
  
-   <span data-ttu-id="3bbd2-113">**シナリオ 2 です。**</span><span class="sxs-lookup"><span data-stu-id="3bbd2-113">**Scenario 2.**</span></span> <span data-ttu-id="3bbd2-114">開発者は、自動的に次のように、新しい公開キー トークンの代わりに、スクリプトを構成できます。 スクリプトの先頭には、公開キー トークンの置換ユーティリティを呼び出すと、公開キー トークンを含む .snk ファイルをポイントします。</span><span class="sxs-lookup"><span data-stu-id="3bbd2-114">The developer can configure the script to automatically substitute the new public key token, as follows: At the start of the script, invoke the Replace Public Key Token utility and point it to a .snk file that contains the public key token.</span></span> <span data-ttu-id="3bbd2-115">公開キー トークンを表す環境変数 %NEWTOKEN% をスクリプト内で使用します。</span><span class="sxs-lookup"><span data-stu-id="3bbd2-115">Within the script, use the environment variable %NEWTOKEN% to represent the public key token.</span></span> <span data-ttu-id="3bbd2-116">スクリプトの実行時に、ユーティリティは、.snk ファイルから公開キー トークンの値を抽出し、その値を環境変数 %NEWTOKEN% に設定します。</span><span class="sxs-lookup"><span data-stu-id="3bbd2-116">When the script runs, the utility extracts the value of the public key token from the .snk file and sets it into an environment variable %NEWTOKEN%.</span></span> <span data-ttu-id="3bbd2-117">スクリプトの実行時に、%NEWTOKEN% の各インスタンスが、指定された .snk ファイルの公開キー トークンに置き換えられます。</span><span class="sxs-lookup"><span data-stu-id="3bbd2-117">When the script runs, each instance of %NEWTOKEN% will be with substituted with the public key token from the specified .snk file.</span></span> <span data-ttu-id="3bbd2-118">例:</span><span class="sxs-lookup"><span data-stu-id="3bbd2-118">For example:</span></span>  
  
    ```  
    ReplacePKT.bat key.snk  
    ...  
    ...  
    gacutil /u Assembly, ... PublicKey=%NEWTOKEN% ...  
    ```  
  
## <a name="location-in-sdk"></a><span data-ttu-id="3bbd2-119">SDK でのパス</span><span class="sxs-lookup"><span data-stu-id="3bbd2-119">Location in SDK</span></span>  
 <span data-ttu-id="3bbd2-120">公開キー トークンの置換ユーティリティは次の場所にあります。</span><span class="sxs-lookup"><span data-stu-id="3bbd2-120">The Replace Public Key Token utility is located in:</span></span>  
  
 [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]<span data-ttu-id="3bbd2-121">SDK\Utilities\ReplacePublicKeyToken\\です。</span><span class="sxs-lookup"><span data-stu-id="3bbd2-121">SDK\Utilities\ReplacePublicKeyToken\\.</span></span>  
  
 <span data-ttu-id="3bbd2-122">公開キー トークンの置換ユーティリティは次の 3 つのファイルから構成されます。</span><span class="sxs-lookup"><span data-stu-id="3bbd2-122">The Replace Public Key Token utility comprises three files:</span></span>  
  
-   <span data-ttu-id="3bbd2-123">ReplacePKT.bat</span><span class="sxs-lookup"><span data-stu-id="3bbd2-123">ReplacePKT.bat</span></span>  
  
-   <span data-ttu-id="3bbd2-124">ReplacePKT.vbs</span><span class="sxs-lookup"><span data-stu-id="3bbd2-124">ReplacePKT.vbs</span></span>  
  
-   <span data-ttu-id="3bbd2-125">ReplacePKT.wsf</span><span class="sxs-lookup"><span data-stu-id="3bbd2-125">ReplacePKT.wsf</span></span>  
  
## <a name="procedures"></a><span data-ttu-id="3bbd2-126">手順</span><span class="sxs-lookup"><span data-stu-id="3bbd2-126">Procedures</span></span>  
 <span data-ttu-id="3bbd2-127">シナリオ 1 の説明に従って、ファイル内の公開キー トークンまたはプレースホルダーのインスタンスを、.snk ファイルから抽出した公開キー トークンに置き換えるには、次の手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="3bbd2-127">Use the following procedure to replace all instances of a public key token or a placeholder in a file with a public key token extracted from an .snk file, as described in Scenario 1.</span></span>  
  
#### <a name="to-replace-instances-of-a-public-key-token-or-a-placeholder-in-a-file"></a><span data-ttu-id="3bbd2-128">ファイル内の公開キー トークンまたはプレースホルダーのインスタンスを置き換えるには</span><span class="sxs-lookup"><span data-stu-id="3bbd2-128">To replace instances of a public key token or a placeholder in a file</span></span>  
  
1.  <span data-ttu-id="3bbd2-129">公開キー トークンの置換ユーティリティの 3 つのファイル (ReplacePKT.bat、ReplacePKT.vbs、および ReplacePKT.wsf)、スクリプト ファイル、および .snk ファイルがローカル コンピューターに存在していることを確認します。</span><span class="sxs-lookup"><span data-stu-id="3bbd2-129">Make sure that the three Replace Public Key Token utility files (ReplacePKT.bat, ReplacePKT.vbs, ReplacePKT.wsf), the script file, and the .snk file are all available from the local computer.</span></span>  
  
2.  <span data-ttu-id="3bbd2-130">コマンド ウィンドウで、公開キーの置換ユーティリティのファイルを含むフォルダーにディレクトリを変更します。</span><span class="sxs-lookup"><span data-stu-id="3bbd2-130">In a command window, change the directory to the folder containing the Replace Public Key utility files.</span></span>  
  
3.  <span data-ttu-id="3bbd2-131">コマンド プロンプトから次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="3bbd2-131">From a command prompt, run the following command:</span></span>  
  
4.  <span data-ttu-id="3bbd2-132">**ReplacePKT \<**  *.snk ファイル*  **\> \<**  *古い公開キー トークン*  **\> \<**  *ファイルを置き換える***\>**</span><span class="sxs-lookup"><span data-stu-id="3bbd2-132">**ReplacePKT \<** *.snk file* **\> \<** *old public key token* **\> \<** *file to replace* **\>**</span></span>  
  
    |<span data-ttu-id="3bbd2-133">オプション</span><span class="sxs-lookup"><span data-stu-id="3bbd2-133">Option</span></span>|<span data-ttu-id="3bbd2-134">Description</span><span class="sxs-lookup"><span data-stu-id="3bbd2-134">Description</span></span>|  
    |------------|-----------------|  
    |<span data-ttu-id="3bbd2-135">**\<***.snk ファイル***\>**</span><span class="sxs-lookup"><span data-stu-id="3bbd2-135">**\<** *.snk file* **\>**</span></span>|<span data-ttu-id="3bbd2-136">既存の公開キー トークンまたはプレースホルダーと置き換える公開キー トークンが含まれている .snk ファイルの完全パス。</span><span class="sxs-lookup"><span data-stu-id="3bbd2-136">Full path of the .snk file containing the public key token that you want substitute for the existing public key token or placeholder.</span></span>|  
    |<span data-ttu-id="3bbd2-137">**\<***古い公開キー トークン***\>**</span><span class="sxs-lookup"><span data-stu-id="3bbd2-137">**\<** *old public key token* **\>**</span></span>|<span data-ttu-id="3bbd2-138">置換対象の公開キー トークンまたはプレースホルダー。</span><span class="sxs-lookup"><span data-stu-id="3bbd2-138">Public key token or placeholder that you want to replace.</span></span>|  
    |<span data-ttu-id="3bbd2-139">**\<***ファイルを置き換える***\>**</span><span class="sxs-lookup"><span data-stu-id="3bbd2-139">**\<** *file to replace* **\>**</span></span>|<span data-ttu-id="3bbd2-140">置換対象の公開キー トークンまたはプレースホルダーが含まれているファイルの完全パス。</span><span class="sxs-lookup"><span data-stu-id="3bbd2-140">Full path of the file in which you want to replace the public key token or placeholder.</span></span>|  
  
     <span data-ttu-id="3bbd2-141">例:</span><span class="sxs-lookup"><span data-stu-id="3bbd2-141">Example:</span></span>  
  
     <span data-ttu-id="3bbd2-142">**ReplacePKT.bat C:\Tokens\MyToken.snk 12ab3456cd789e12 C:\Scripts\MyScript.vbs**</span><span class="sxs-lookup"><span data-stu-id="3bbd2-142">**ReplacePKT.bat C:\Tokens\MyToken.snk 12ab3456cd789e12 C:\Scripts\MyScript.vbs**</span></span>  
  
 <span data-ttu-id="3bbd2-143">シナリオ 2 の説明に従って、.snk ファイルから抽出した公開キー トークンを使用するスクリプト内の環境変数を自動的に設定するには、次の手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="3bbd2-143">Use the following procedure to automatically set an environment variable in a script that uses a public key token derived from an .snk file, as described in Scenario 2.</span></span>  
  
#### <a name="to-set-an-environment-variable-that-uses-a-public-key-token"></a><span data-ttu-id="3bbd2-144">公開キー トークンを使用する環境変数を設定するには</span><span class="sxs-lookup"><span data-stu-id="3bbd2-144">To set an environment variable that uses a public key token</span></span>  
  
1.  <span data-ttu-id="3bbd2-145">スクリプト ファイルの先頭に次のコード行を追加します。</span><span class="sxs-lookup"><span data-stu-id="3bbd2-145">At the beginning of your script file, add the following line of code:</span></span>  
  
    ```  
    ReplacePKT <filename>.snk  
    ```  
  
     <span data-ttu-id="3bbd2-146">ここで\< *filename* \>公開キー トークンを取得する .snk ファイルの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="3bbd2-146">Where \<*filename*\> is the name of the .snk file from which to derive the public key token.</span></span>  
  
    ```  
    Example: ReplacePKT.bat MyToken.snk  
    ```  
  
2.  <span data-ttu-id="3bbd2-147">公開キー トークンを表す `%NEWTOKEN%` をスクリプト ファイル内で使用します。</span><span class="sxs-lookup"><span data-stu-id="3bbd2-147">In your script file, use `%NEWTOKEN%` to represent the public key token.</span></span>  
  
     <span data-ttu-id="3bbd2-148">例:</span><span class="sxs-lookup"><span data-stu-id="3bbd2-148">Example:</span></span>  
  
    ```  
    PublicKey=%NEWTOKEN%  
    ```  
  
3.  <span data-ttu-id="3bbd2-149">スクリプト ファイルをユーザーに配布する場合は、公開キー トークンの置換ユーティリティを構成する 3 つのファイル (ReplacePKT.bat、ReplacePKT.vbs、および ReplacePKT.wsf) と共に配布します。</span><span class="sxs-lookup"><span data-stu-id="3bbd2-149">When you deliver your script file to your users, include the three files that comprise the Replace Public Key Token utility (ReplacePKT.bat, ReplacePKT.vbs, ReplacePKT.wsf).</span></span> <span data-ttu-id="3bbd2-150">スクリプト コピーのユーザーが、スクリプトを実行する前に、これらのファイルをファイル システム上の同一のフォルダーにコピーしていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="3bbd2-150">Make sure that users of your script copy all of the files to the same folder on the file system before running your script.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3bbd2-151">参照</span><span class="sxs-lookup"><span data-stu-id="3bbd2-151">See Also</span></span>  
 [<span data-ttu-id="3bbd2-152">SDK のユーティリティ</span><span class="sxs-lookup"><span data-stu-id="3bbd2-152">Utilities in the SDK</span></span>](../core/utilities-in-the-sdk.md)