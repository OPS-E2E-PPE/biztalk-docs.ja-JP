---
title: "サイド バイ サイドのバージョン管理を使用してマップを更新する方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 7b0e377f-92ab-483e-9f3c-222c7b5ac0b1
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6d463823a7038e1ead7e2de323da97eda372db76
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-update-a-map-using-side-by-side-versioning"></a><span data-ttu-id="9013a-102">サイド バイ サイドのバージョン管理を使用してマップを更新する方法</span><span class="sxs-lookup"><span data-stu-id="9013a-102">How to Update a Map Using Side-by-Side Versioning</span></span>
<span data-ttu-id="9013a-103">その場合は、バインドに使用されるバージョンを含めるに厳密な名前の完全修飾 (FQSN) で、マップなど、いくつかの BizTalk アイテムが選択されます。</span><span class="sxs-lookup"><span data-stu-id="9013a-103">Some BizTalk artifacts, such as maps, are chosen by fully-qualified strong name (FQSN), in which case the bindings include the version used.</span></span> <span data-ttu-id="9013a-104">これにより、サイド バイ サイドで共存させる 2 つ以上のマップ、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールです。</span><span class="sxs-lookup"><span data-stu-id="9013a-104">This allows two or more maps to coexist side by side in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span> <span data-ttu-id="9013a-105">その結果、受信場所のプロパティにマッピングが受信または送信マップのマップの 1 つを送信ポートのプロパティで選択できます。</span><span class="sxs-lookup"><span data-stu-id="9013a-105">As a result, you can select one of the maps for inbound mapping in the receive location properties or outbound mapping in the send port properties.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="9013a-106">前提条件</span><span class="sxs-lookup"><span data-stu-id="9013a-106">Prerequisites</span></span>  
 <span data-ttu-id="9013a-107">このトピックの手順を実行するには、BizTalk Server 管理者グループのメンバーであるアカウントを使用してログオンする必要があります。</span><span class="sxs-lookup"><span data-stu-id="9013a-107">To perform the procedures in this topic, you must be logged on with an account that is a member of the BizTalk Server Administrators group.</span></span>  
  
### <a name="to-add-a-second-map-side-by-side-to-an-existing-map"></a><span data-ttu-id="9013a-108">2 つ目のマップ サイド バイ サイドを既存のマップに追加するには</span><span class="sxs-lookup"><span data-stu-id="9013a-108">To add a second map side by side to an existing map</span></span>  
  
1.  <span data-ttu-id="9013a-109">Visual Studio を開き、マップを含むプロジェクトを開きます。</span><span class="sxs-lookup"><span data-stu-id="9013a-109">Open Visual Studio, and then open the project containing the map.</span></span>  
  
2.  <span data-ttu-id="9013a-110">アセンブリにマップを開き、コード マップに変更します。</span><span class="sxs-lookup"><span data-stu-id="9013a-110">Open the map in the assembly, and make a code change to the map.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="9013a-111">元のオーケストレーションは、マップを呼び出すし、マップの参照はハードコードされては、オーケストレーション自体のコードを変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9013a-111">If you call a map from an orchestration, and the map reference is hard-coded, you may need to make code changes to the orchestration itself.</span></span>  
  
3.  <span data-ttu-id="9013a-112">アセンブリのバージョン番号を変更します。</span><span class="sxs-lookup"><span data-stu-id="9013a-112">Change the version number of the assembly:</span></span>  
  
    1.  <span data-ttu-id="9013a-113">ソリューション エクスプ ローラーで、BizTalk プロジェクトを右クリックし、をクリックして**プロパティ**です。</span><span class="sxs-lookup"><span data-stu-id="9013a-113">In Solution Explorer, right-click the BizTalk project, and then click **Properties**.</span></span>  
  
    2.  <span data-ttu-id="9013a-114">**プロジェクト デザイナー**をクリックして、**アプリケーション**タブです。</span><span class="sxs-lookup"><span data-stu-id="9013a-114">In the **Project Designer**, click the **Application** tab.</span></span>  
  
    3.  <span data-ttu-id="9013a-115">右側のウィンドウでをクリックして**アセンブリ情報**です。</span><span class="sxs-lookup"><span data-stu-id="9013a-115">In the right pane, click **Assembly Information**.</span></span>  
  
    4.  <span data-ttu-id="9013a-116">**アセンブリ情報** ダイアログ ボックスで、値を指定、**アセンブリ バージョン**アセンブリのバージョン番号を変更するフィールドです。</span><span class="sxs-lookup"><span data-stu-id="9013a-116">In the **Assembly Information** dialog box, specify values for the **Assembly Version** field to change the assembly version number.</span></span> <span data-ttu-id="9013a-117">メジャー バージョンまたはマイナー バージョン番号のみを変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9013a-117">You should change only the major or minor version number.</span></span> <span data-ttu-id="9013a-118">メジャー バージョン番号は、シーケンスの最初の桁 (***n***.0.0.0); マイナー バージョン番号は、シーケンス内の 2 番目の数字 (0*** 。n ***.0.0) です。</span><span class="sxs-lookup"><span data-stu-id="9013a-118">The major version number is the first digit in the sequence (***n***.0.0.0); the minor version number is the second digit in the sequence (0.***n***.0.0).</span></span>  
  
    5.  <span data-ttu-id="9013a-119">をクリックして**OK**を閉じる、**アセンブリ情報** ダイアログ ボックス。</span><span class="sxs-lookup"><span data-stu-id="9013a-119">Click **OK** to close the **Assembly Information** dialog box.</span></span>  
  
4.  <span data-ttu-id="9013a-120">アセンブリをコンパイルします。</span><span class="sxs-lookup"><span data-stu-id="9013a-120">Compile the assembly.</span></span>  
  
5.  <span data-ttu-id="9013a-121">グループ (とすべてのコンピューター) にアセンブリを展開します。</span><span class="sxs-lookup"><span data-stu-id="9013a-121">Deploy the assembly to the group (and all computers).</span></span>  
  
## <a name="modifying-a-map-to-reflect-updated-version-numbers"></a><span data-ttu-id="9013a-122">新しいバージョン番号を反映するようにマップを変更します。</span><span class="sxs-lookup"><span data-stu-id="9013a-122">Modifying a Map to Reflect Updated Version Numbers</span></span>  
 <span data-ttu-id="9013a-123">.NET アセンブリは、スクリプト functoid を使用して、マップ内から呼び出すことができます。</span><span class="sxs-lookup"><span data-stu-id="9013a-123">.NET assemblies can be invoked from within a map by using the Scripting functoid.</span></span> <span data-ttu-id="9013a-124">この方法では高い柔軟性が得られ、開発者はカスタム マッピングに関するさまざまな問題を解決することができます。</span><span class="sxs-lookup"><span data-stu-id="9013a-124">This provides a great deal of flexibility and enables the developer to solve many different custom mapping problems.</span></span> <span data-ttu-id="9013a-125">マップに unique 制約を課します-内部でアセンブリの型名だけでなく、呼び出されている完全なアセンブリ バージョン番号を参照して必要があります。</span><span class="sxs-lookup"><span data-stu-id="9013a-125">It also imposes a unique constraint on the map—it must internally reference not only the assembly type name but also the full assembly version number being invoked.</span></span> <span data-ttu-id="9013a-126">この結果、マップによって呼び出されるアセンブリのバージョン番号が変わると、そのアセンブリを参照するすべてのリンクが壊れることになります。</span><span class="sxs-lookup"><span data-stu-id="9013a-126">As a consequence, if the version number of the assembly called by the map changes, all of the links that reference the assembly will break.</span></span>  
  
 <span data-ttu-id="9013a-127">この問題を回避するには、アセンブリが、マップからの呼び出しに必要な場合に、特定のアセンブリがマップ機能とこのアセンブリのアセンブリ バージョン番号を修正することのみを保持するために作成されたことをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="9013a-127">To avoid this issue we recommend that if assemblies are required to be called from a map, a specific assembly is created to hold only map functionality and that the assembly version number of this assembly is fixed.</span></span> <span data-ttu-id="9013a-128">こうすると、マップを崩すことなく他のヘルパー関数ではアセンブリ バージョン番号を更新できます。</span><span class="sxs-lookup"><span data-stu-id="9013a-128">In this way, other helper functions can have the assembly version updated without breaking the maps.</span></span>  
  
 <span data-ttu-id="9013a-129">マップを開発した後、マップから参照するアセンブリが変更される場合については、マップ エディター外でマップ ファイルを更新し、新しいバージョン番号を反映することを検討してください。</span><span class="sxs-lookup"><span data-stu-id="9013a-129">If an assembly referenced from a map is changed after map development then consider updating the map file outside of the Map Editor to reflect the updated version numbers.</span></span>  
  
#### <a name="to-modify-a-map-file-to-reflect-updated-version-numbers"></a><span data-ttu-id="9013a-130">更新されたバージョン番号を反映するようにマップ ファイルを変更するには</span><span class="sxs-lookup"><span data-stu-id="9013a-130">To modify a map file to reflect updated version numbers</span></span>  
  
1.  <span data-ttu-id="9013a-131">使用して、**開始**] メニューの [開いている**メモ帳**です。</span><span class="sxs-lookup"><span data-stu-id="9013a-131">Using the **Start** menu, open **Notepad**.</span></span>  
  
2.  <span data-ttu-id="9013a-132">**メモ帳**の**ファイル** メニューのをクリックして**開く**です。</span><span class="sxs-lookup"><span data-stu-id="9013a-132">In **Notepad**, on the **File** menu, click **Open**.</span></span> <span data-ttu-id="9013a-133">**開く** ダイアログ ボックスで、マップ ファイルをクリックして、変更する**開く**です。</span><span class="sxs-lookup"><span data-stu-id="9013a-133">In the **Open** dialog box, select the map file you want to modify, and then click **Open**.</span></span>  
  
3.  <span data-ttu-id="9013a-134">**[編集]** メニューの **[検索]**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9013a-134">On the **Edit** menu, click **Find**.</span></span> <span data-ttu-id="9013a-135">**検索** ダイアログ ボックスに、入力**アセンブリ =**、クリックして**次を検索**です。</span><span class="sxs-lookup"><span data-stu-id="9013a-135">In the **Find** dialog box, enter **Assembly=**, and then click **Find Next**.</span></span>  
  
4.  <span data-ttu-id="9013a-136">外部アセンブリへのスクリプト参照がある場合、メモ帳では次のような XML 要素が検索されます。</span><span class="sxs-lookup"><span data-stu-id="9013a-136">If there is a script reference to an external assembly, Notepad should find an XML element like the following:</span></span>  
  
    ```  
    <Script Language="ExternalAssembly" Assembly="Contoso.Scripts, Version=2.0.0.0, Culture=neutral, PublicKeyToken=  
    <token>  
    " Class="Contoso.Scripts" Function="CalculateValue" AssemblyPath="Contoso.Scripts.dll"/>  
    ```  
  
5.  <span data-ttu-id="9013a-137">バージョン番号を更新します。</span><span class="sxs-lookup"><span data-stu-id="9013a-137">Update the version number.</span></span> <span data-ttu-id="9013a-138">複数のインスタンスがある場合は、使用**置換**上、**編集**メニュー。</span><span class="sxs-lookup"><span data-stu-id="9013a-138">If there are multiple instances, use **Replace** on the **Edit** menu.</span></span>  
  
6.  <span data-ttu-id="9013a-139">ファイルを保存します。</span><span class="sxs-lookup"><span data-stu-id="9013a-139">Save the file.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="9013a-140">これで、マップ エディターを使用してマップを開くことができます。</span><span class="sxs-lookup"><span data-stu-id="9013a-140">You can now open the map using the Map Editor.</span></span>