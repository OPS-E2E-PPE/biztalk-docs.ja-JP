---
title: SSO クライアント ユーティリティをインストールする方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- installing, SSO
- SSO, client utility
- client utility [SSO]
- SSO, installing
ms.assetid: e14d257e-2fde-46af-b90c-5dbc0884536b
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 674ecc3857fe9e5b5cbef2914aec875f350d7de5
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37003963"
---
# <a name="how-to-install-the-sso-client-utility"></a><span data-ttu-id="c4f4e-102">SSO クライアント ユーティリティをインストールする方法</span><span class="sxs-lookup"><span data-stu-id="c4f4e-102">How to Install the SSO Client Utility</span></span>
<span data-ttu-id="c4f4e-103">スタンドアロンの SSO クライアント ユーティリティ (コマンド ライン ユーティリティ ベースおよびユーザー インターフェイス ベース) を使用すると、エンド ユーザーが SSO データベースでクライアントのマッピングを構成できます。</span><span class="sxs-lookup"><span data-stu-id="c4f4e-103">The stand-alone SSO client utility (command-line utility and user interface-based) allows end users to configure their client mappings in the SSO database.</span></span> <span data-ttu-id="c4f4e-104">クライアント ユーティリティは、SSO 管理機能と一緒にインストールされる自己展開型ファイル (SSOClientInstall.exe) からインストールできます。</span><span class="sxs-lookup"><span data-stu-id="c4f4e-104">You can install the client utility from a self-extracting file (SSOClientInstall.exe) which is installed with the SSO administration feature.</span></span> <span data-ttu-id="c4f4e-105">管理者は、ネットワーク共有上にインストーラ パッケージのコピーを配置することで、クライアント ユーザーがインストーラ パッケージを使用できるようにすることもできます。</span><span class="sxs-lookup"><span data-stu-id="c4f4e-105">Administrators can also make the installer package available to client users by placing a copy of the installer package on a network share.</span></span>  
  
 <span data-ttu-id="c4f4e-106">SSO クライアント ユーティリティをインストールするには、クライアント コンピュータで次のオペレーティング システムのいずれかを実行している必要があります。</span><span class="sxs-lookup"><span data-stu-id="c4f4e-106">To install the SSO client utility, you must be running one of the following operating systems on the client computer:</span></span>  
  
- [!INCLUDE[btsPlatformsComApis](../includes/btsplatformscomapis-md.md)]  
  
- <span data-ttu-id="c4f4e-107">
  [!INCLUDE[btsDotNetFramework3.5](../includes/btsdotnetframework3-5-md.md)] または [!INCLUDE[netfx40_short](../includes/netfx40-short-md.md)] (UI ベースの SSO クライアント ユーティリティを使用する場合、またはエンタープライズ SSO の相互運用マネージド コンポーネントを利用する場合にのみ必要です)。</span><span class="sxs-lookup"><span data-stu-id="c4f4e-107">[!INCLUDE[btsDotNetFramework3.5](../includes/btsdotnetframework3-5-md.md)] or [!INCLUDE[netfx40_short](../includes/netfx40-short-md.md)] (only necessary if you are using the UI-based SSO Client Utility or for leveraging the managed interoperability component of Enterprise SSO).</span></span>  
  
  <span data-ttu-id="c4f4e-108">SSO クライアント ユーティリティをインストールした後からを起動できる、**開始**メニューをクリックして**プログラム**、 **Microsoft エンタープライズ シングル サインオン**、し**SSO クライアント ユーティリティ**します。</span><span class="sxs-lookup"><span data-stu-id="c4f4e-108">After installing the SSO Client Utility, you can launch it from the **Start** menu by clicking **Programs**, **Microsoft Enterprise Single Sign-On**, and then **SSO Client Utility**.</span></span>  
  
### <a name="to-install-the-sso-client-utility"></a><span data-ttu-id="c4f4e-109">SSO クライアント ユーティリティをインストールするには</span><span class="sxs-lookup"><span data-stu-id="c4f4e-109">To install the SSO client utility</span></span>  
  
1.  <span data-ttu-id="c4f4e-110">インストーラ パッケージ SSOClientInstall をダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="c4f4e-110">Double-click the installer package SSOClientInstall.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="c4f4e-111">このファイルが企業内のどこにあるのかについては、エンタープライズ シングル サインオン管理者に問い合わせてください。</span><span class="sxs-lookup"><span data-stu-id="c4f4e-111">Ask your Enterprise Single Sign-On Administrator for the location of this file in your enterprise.</span></span>  
  
     <span data-ttu-id="c4f4e-112">**WinZip Self-extractor**プログラムが表示されます。</span><span class="sxs-lookup"><span data-stu-id="c4f4e-112">The **WinZip Self-Extractor** program appears.</span></span>  
  
2.  <span data-ttu-id="c4f4e-113">フォルダー、ファイルを解凍し、をクリックして選択します**Unzip**します。</span><span class="sxs-lookup"><span data-stu-id="c4f4e-113">Select the folder where you want to unzip the files, and click **Unzip**.</span></span>  
  
     <span data-ttu-id="c4f4e-114">ファイルは一時フォルダに解凍することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="c4f4e-114">It is recommended to unzip the files in a temporary folder.</span></span>  
  
     <span data-ttu-id="c4f4e-115">**エンタープライズ シングル サインオン クライアント セットアップ**プログラムが表示されます。</span><span class="sxs-lookup"><span data-stu-id="c4f4e-115">The **Enterprise Single Sign-On Client Setup** program appears.</span></span>  
  
3.  <span data-ttu-id="c4f4e-116">**エンタープライズ シングル サインオン クライアントへようこそ**  ページで **次**します。</span><span class="sxs-lookup"><span data-stu-id="c4f4e-116">On **the Welcome to the Enterprise Single Sign-On Client** page, click **Next**.</span></span>  
  
4.  <span data-ttu-id="c4f4e-117">使用許諾契約書 ページで、次のようにクリックします。**本ライセンス契約の条項に同意**、 をクリックし、**次**。</span><span class="sxs-lookup"><span data-stu-id="c4f4e-117">On the License Agreement page, click **I accept the terms of this license agreement**, and then click **Next**.</span></span>  
  
5.  <span data-ttu-id="c4f4e-118">**ユーザー情報** ページで、ユーザー名、組織の名前を入力してをクリックし、**次**します。</span><span class="sxs-lookup"><span data-stu-id="c4f4e-118">On the **User Information** page, type your user name, organization name, and then click **Next**.</span></span>  
  
6.  <span data-ttu-id="c4f4e-119">**インストールの開始**] ページで [**インストール**します。</span><span class="sxs-lookup"><span data-stu-id="c4f4e-119">On the **Start Installation** page, click **Install**.</span></span>  
  
7.  <span data-ttu-id="c4f4e-120">**エンタープライズ シングル サインオン クライアント ウィザードの完了**] ページで [**完了**します。</span><span class="sxs-lookup"><span data-stu-id="c4f4e-120">On the **Completing the Enterprise Single Sign-On Client Wizard** page, click **Finish**.</span></span>  
  
8.  <span data-ttu-id="c4f4e-121">次のいずれかの手順を実行し、SSO サーバーを指定します。</span><span class="sxs-lookup"><span data-stu-id="c4f4e-121">Specify the SSO server by doing either of the following:</span></span>  
  
    -   <span data-ttu-id="c4f4e-122">ENTSSO 管理の MMC スナップインを開きます。</span><span class="sxs-lookup"><span data-stu-id="c4f4e-122">Open the ENTSSO Administration MMC Snap-In.</span></span> <span data-ttu-id="c4f4e-123">**SSO サーバーの選択**ダイアログが表示されます。</span><span class="sxs-lookup"><span data-stu-id="c4f4e-123">The **Select SSO Server** dialog will appear.</span></span> <span data-ttu-id="c4f4e-124">管理操作の実行時に接続する SSO サーバーについて、名前を入力するか、または参照します。</span><span class="sxs-lookup"><span data-stu-id="c4f4e-124">Enter or browse to the SSO Server that you want to connect to when you perform administration operations.</span></span> <span data-ttu-id="c4f4e-125">コンピューターのすべてのユーザーの SSO サーバーを指定する**すべてのユーザーの SSO サーバーを設定**します。</span><span class="sxs-lookup"><span data-stu-id="c4f4e-125">To specify the SSO Server for all users on the machine, select **Set SSO Server for all users**.</span></span>  
  
         <span data-ttu-id="c4f4e-126">OR</span><span class="sxs-lookup"><span data-stu-id="c4f4e-126">OR</span></span>  
  
    -   <span data-ttu-id="c4f4e-127">コマンド プロンプトで「`ssomanage –server`目的の SSO サーバーを指定します。</span><span class="sxs-lookup"><span data-stu-id="c4f4e-127">At a command prompt, type `ssomanage –server` to specify the SSO server desired.</span></span> <span data-ttu-id="c4f4e-128">入力することも`ssomanage -serverall`管理操作を実行するときにこのコンピューターのすべてのユーザーが接続する SSO サーバーを指定します。</span><span class="sxs-lookup"><span data-stu-id="c4f4e-128">You can also type `ssomanage -serverall` to specify the SSO server that all users of this computer will connect to when performing administration operations.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c4f4e-129">参照</span><span class="sxs-lookup"><span data-stu-id="c4f4e-129">See Also</span></span>  
 <span data-ttu-id="c4f4e-130">[SSO 管理コンポーネントをインストールする方法](../core/how-to-install-the-sso-administration-component.md) </span><span class="sxs-lookup"><span data-stu-id="c4f4e-130">[How to Install the SSO Administration Component](../core/how-to-install-the-sso-administration-component.md) </span></span>  
 <span data-ttu-id="c4f4e-131">[SSO を構成します。](../core/configuring-sso.md) </span><span class="sxs-lookup"><span data-stu-id="c4f4e-131">[Configuring SSO](../core/configuring-sso.md) </span></span>  
 [<span data-ttu-id="c4f4e-132">SSO のインストール</span><span class="sxs-lookup"><span data-stu-id="c4f4e-132">Installing SSO</span></span>](../core/installing-sso.md)