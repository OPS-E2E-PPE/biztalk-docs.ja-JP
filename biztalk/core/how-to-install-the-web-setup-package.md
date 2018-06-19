---
title: Web セットアップ パッケージをインストールする方法 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- deploying, Web services
- Web services, deploying
- Web services, installing
ms.assetid: c6b38a2f-ad07-4ccd-b267-9e3510df88c3
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 21fbacd76598a3a86cfa70b4761bc74420afe561
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22254130"
---
# <a name="how-to-install-the-web-setup-package"></a><span data-ttu-id="d34a9-102">Web セットアップ パッケージをインストールする方法</span><span class="sxs-lookup"><span data-stu-id="d34a9-102">How to Install the Web Setup Package</span></span>
<span data-ttu-id="d34a9-103">送信先コンピュータで Web サービスをセットアップするには、配布フォルダの内容を使用します。</span><span class="sxs-lookup"><span data-stu-id="d34a9-103">Use the contents of the distribution folder to setup the Web service on a destination computer.</span></span>  
  
### <a name="to-install-the-web-setup-package"></a><span data-ttu-id="d34a9-104">Web セットアップ パッケージをインストールするには</span><span class="sxs-lookup"><span data-stu-id="d34a9-104">To install the Web setup package</span></span>  
  
1.  <span data-ttu-id="d34a9-105">セットアップ先コンピューターに配布フォルダにコピーします。</span><span class="sxs-lookup"><span data-stu-id="d34a9-105">Copy the distribution folder onto the destination computer.</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="d34a9-106">送信先コンピュータには、BizTalk Server ランタイムがインストールされ、グローバル アセンブリ キャッシュに必要な BizTalk アセンブリが展開されてインストールされていることが必要です。</span><span class="sxs-lookup"><span data-stu-id="d34a9-106">The destination computer must have the BizTalk Server runtime installed and the necessary BizTalk assemblies deployed and installed in the global assembly cache.</span></span>  
  
2.  <span data-ttu-id="d34a9-107">.MSI ファイルを実行して Web サービスをインストールし、セットアップ ウィザードの指示に従って操作します。</span><span class="sxs-lookup"><span data-stu-id="d34a9-107">Run the .MSI file to install the Web service and follow the setup wizard prompts.</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="d34a9-108">ウィザードで仮想ディレクトリについて確認するメッセージが表示されたら、"_Setup" サフィックスを削除します。サフィックスを削除することで、確実に受信場所のアドレスが Web サービスの .asmx ファイルと一致するようになります。</span><span class="sxs-lookup"><span data-stu-id="d34a9-108">Remove the "_Setup" suffix when the wizard prompts you for the virtual directory.Removing the suffix ensures that the receive location addresses match the Web service .asmx files.</span></span>  
  
3.  <span data-ttu-id="d34a9-109">仮想ディレクトリのセキュリティ設定が正しく、認証に使用できることを確認します。</span><span class="sxs-lookup"><span data-stu-id="d34a9-109">Verify that the security settings for the virtual directory are correct for authorization.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d34a9-110">参照</span><span class="sxs-lookup"><span data-stu-id="d34a9-110">See Also</span></span>  
 [<span data-ttu-id="d34a9-111">非 Visual Studio コンピューターに公開された Web サービスを展開します。</span><span class="sxs-lookup"><span data-stu-id="d34a9-111">Deploying Published Web Services on a Non-Visual Studio Computer</span></span>](../core/deploying-published-web-services-on-a-non-visual-studio-computer.md)