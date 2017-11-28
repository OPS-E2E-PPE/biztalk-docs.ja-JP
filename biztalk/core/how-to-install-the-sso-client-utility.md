---
title: "SSO クライアント ユーティリティをインストールする方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- installing, SSO
- SSO, client utility
- client utility [SSO]
- SSO, installing
ms.assetid: e14d257e-2fde-46af-b90c-5dbc0884536b
caps.latest.revision: "14"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4eba4e0747c9566c5303e04602d957173cc56052
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-install-the-sso-client-utility"></a><span data-ttu-id="1b241-102">SSO クライアント ユーティリティをインストールする方法</span><span class="sxs-lookup"><span data-stu-id="1b241-102">How to Install the SSO Client Utility</span></span>
<span data-ttu-id="1b241-103">スタンドアロンの SSO クライアント ユーティリティ (コマンド ライン ユーティリティ ベースおよびユーザー インターフェイス ベース) を使用すると、エンド ユーザーが SSO データベースでクライアントのマッピングを構成できます。</span><span class="sxs-lookup"><span data-stu-id="1b241-103">The stand-alone SSO client utility (command-line utility and user interface-based) allows end users to configure their client mappings in the SSO database.</span></span> <span data-ttu-id="1b241-104">クライアント ユーティリティは、SSO 管理機能と一緒にインストールされる自己展開型ファイル (SSOClientInstall.exe) からインストールできます。</span><span class="sxs-lookup"><span data-stu-id="1b241-104">You can install the client utility from a self-extracting file (SSOClientInstall.exe) which is installed with the SSO administration feature.</span></span> <span data-ttu-id="1b241-105">管理者は、ネットワーク共有上にインストーラ パッケージのコピーを配置することで、クライアント ユーザーがインストーラ パッケージを使用できるようにすることもできます。</span><span class="sxs-lookup"><span data-stu-id="1b241-105">Administrators can also make the installer package available to client users by placing a copy of the installer package on a network share.</span></span>  
  
 <span data-ttu-id="1b241-106">SSO クライアント ユーティリティをインストールするには、クライアント コンピュータで次のオペレーティング システムのいずれかを実行している必要があります。</span><span class="sxs-lookup"><span data-stu-id="1b241-106">To install the SSO client utility, you must be running one of the following operating systems on the client computer:</span></span>  
  
-   [!INCLUDE[btsPlatformsComApis](../includes/btsplatformscomapis-md.md)]  
  
-   [!INCLUDE[btsDotNetFramework3.5](../includes/btsdotnetframework3-5-md.md)]<span data-ttu-id="1b241-107"> または [!INCLUDE[netfx40_short](../includes/netfx40-short-md.md)] (UI ベースの SSO クライアント ユーティリティを使用する場合、またはエンタープライズ SSO の相互運用マネージ コンポーネントを利用する場合にのみ必要です)。</span><span class="sxs-lookup"><span data-stu-id="1b241-107"> or [!INCLUDE[netfx40_short](../includes/netfx40-short-md.md)] (only necessary if you are using the UI-based SSO Client Utility or for leveraging the managed interoperability component of Enterprise SSO).</span></span>  
  
 <span data-ttu-id="1b241-108">SSO クライアント ユーティリティをインストールした後を実行してから、**開始** をクリックしてメニュー**プログラム**、 **Microsoft エンタープライズ シングル サインオン**、し**SSO クライアント ユーティリティ**です。</span><span class="sxs-lookup"><span data-stu-id="1b241-108">After installing the SSO Client Utility, you can launch it from the **Start** menu by clicking **Programs**, **Microsoft Enterprise Single Sign-On**, and then **SSO Client Utility**.</span></span>  
  
### <a name="to-install-the-sso-client-utility"></a><span data-ttu-id="1b241-109">SSO クライアント ユーティリティをインストールするには</span><span class="sxs-lookup"><span data-stu-id="1b241-109">To install the SSO client utility</span></span>  
  
1.  <span data-ttu-id="1b241-110">インストーラ パッケージ SSOClientInstall をダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="1b241-110">Double-click the installer package SSOClientInstall.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="1b241-111">このファイルが企業内のどこにあるのかについては、エンタープライズ シングル サインオン管理者に問い合わせてください。</span><span class="sxs-lookup"><span data-stu-id="1b241-111">Ask your Enterprise Single Sign-On Administrator for the location of this file in your enterprise.</span></span>  
  
     <span data-ttu-id="1b241-112">**WinZip Self-extractor**プログラムが表示されます。</span><span class="sxs-lookup"><span data-stu-id="1b241-112">The **WinZip Self-Extractor** program appears.</span></span>  
  
2.  <span data-ttu-id="1b241-113">ファイルを解凍し、をクリックする場所のフォルダーを選択**Unzip**です。</span><span class="sxs-lookup"><span data-stu-id="1b241-113">Select the folder where you want to unzip the files, and click **Unzip**.</span></span>  
  
     <span data-ttu-id="1b241-114">ファイルは一時フォルダに解凍することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="1b241-114">It is recommended to unzip the files in a temporary folder.</span></span>  
  
     <span data-ttu-id="1b241-115">**エンタープライズ シングル サインオン クライアント セットアップ**プログラムが表示されます。</span><span class="sxs-lookup"><span data-stu-id="1b241-115">The **Enterprise Single Sign-On Client Setup** program appears.</span></span>  
  
3.  <span data-ttu-id="1b241-116">**エンタープライズ シングル サインオン クライアントへようこそ**  ページで、をクリックして**次**です。</span><span class="sxs-lookup"><span data-stu-id="1b241-116">On **the Welcome to the Enterprise Single Sign-On Client** page, click **Next**.</span></span>  
  
4.  <span data-ttu-id="1b241-117">使用許諾契約書 ページで、をクリックして**本ライセンス契約の条項に同意**、順にクリック**次**です。</span><span class="sxs-lookup"><span data-stu-id="1b241-117">On the License Agreement page, click **I accept the terms of this license agreement**, and then click **Next**.</span></span>  
  
5.  <span data-ttu-id="1b241-118">**ユーザー情報** ページで、ユーザー名、組織名を入力してをクリックして**次**です。</span><span class="sxs-lookup"><span data-stu-id="1b241-118">On the **User Information** page, type your user name, organization name, and then click **Next**.</span></span>  
  
6.  <span data-ttu-id="1b241-119">**インストールの開始**] ページで [**インストール**です。</span><span class="sxs-lookup"><span data-stu-id="1b241-119">On the **Start Installation** page, click **Install**.</span></span>  
  
7.  <span data-ttu-id="1b241-120">**エンタープライズ シングル サインオン クライアント ウィザードの完了**] ページで [**完了**です。</span><span class="sxs-lookup"><span data-stu-id="1b241-120">On the **Completing the Enterprise Single Sign-On Client Wizard** page, click **Finish**.</span></span>  
  
8.  <span data-ttu-id="1b241-121">次のいずれかの手順を実行し、SSO サーバーを指定します。</span><span class="sxs-lookup"><span data-stu-id="1b241-121">Specify the SSO server by doing either of the following:</span></span>  
  
    -   <span data-ttu-id="1b241-122">ENTSSO 管理の MMC スナップインを開きます。</span><span class="sxs-lookup"><span data-stu-id="1b241-122">Open the ENTSSO Administration MMC Snap-In.</span></span> <span data-ttu-id="1b241-123">**SSO サーバーの選択**ダイアログが表示されます。</span><span class="sxs-lookup"><span data-stu-id="1b241-123">The **Select SSO Server** dialog will appear.</span></span> <span data-ttu-id="1b241-124">管理操作の実行時に接続する SSO サーバーについて、名前を入力するか、または参照します。</span><span class="sxs-lookup"><span data-stu-id="1b241-124">Enter or browse to the SSO Server that you want to connect to when you perform administration operations.</span></span> <span data-ttu-id="1b241-125">コンピューター上のすべてのユーザーの SSO サーバーを指定するには、選択**すべてのユーザーの SSO サーバーの設定**です。</span><span class="sxs-lookup"><span data-stu-id="1b241-125">To specify the SSO Server for all users on the machine, select **Set SSO Server for all users**.</span></span>  
  
         <span data-ttu-id="1b241-126">または</span><span class="sxs-lookup"><span data-stu-id="1b241-126">OR</span></span>  
  
    -   <span data-ttu-id="1b241-127">コマンド プロンプトで「`ssomanage –server`を目的の SSO サーバーを指定します。</span><span class="sxs-lookup"><span data-stu-id="1b241-127">At a command prompt, type `ssomanage –server` to specify the SSO server desired.</span></span> <span data-ttu-id="1b241-128">入力することも`ssomanage -serverall`管理操作を実行するときに、このコンピューターのすべてのユーザーが接続する SSO サーバーを指定します。</span><span class="sxs-lookup"><span data-stu-id="1b241-128">You can also type `ssomanage -serverall` to specify the SSO server that all users of this computer will connect to when performing administration operations.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1b241-129">参照</span><span class="sxs-lookup"><span data-stu-id="1b241-129">See Also</span></span>  
 <span data-ttu-id="1b241-130">[SSO 管理コンポーネントをインストールする方法](../core/how-to-install-the-sso-administration-component.md) </span><span class="sxs-lookup"><span data-stu-id="1b241-130">[How to Install the SSO Administration Component](../core/how-to-install-the-sso-administration-component.md) </span></span>  
 <span data-ttu-id="1b241-131">[SSO を構成します。](../core/configuring-sso.md) </span><span class="sxs-lookup"><span data-stu-id="1b241-131">[Configuring SSO](../core/configuring-sso.md) </span></span>  
 [<span data-ttu-id="1b241-132">SSO のインストール</span><span class="sxs-lookup"><span data-stu-id="1b241-132">Installing SSO</span></span>](../core/installing-sso.md)