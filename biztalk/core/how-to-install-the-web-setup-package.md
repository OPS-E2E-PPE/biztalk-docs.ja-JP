---
title: Web セットアップ パッケージをインストールする方法 |Microsoft Docs
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
ms.openlocfilehash: bb29badb7f3966a094b6131d7ecbf4fd41401116
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65384880"
---
# <a name="how-to-install-the-web-setup-package"></a><span data-ttu-id="52260-102">Web セットアップ パッケージをインストールする方法</span><span class="sxs-lookup"><span data-stu-id="52260-102">How to Install the Web Setup Package</span></span>
<span data-ttu-id="52260-103">配布フォルダの内容を使用して、対象のコンピュータで Web サービスをセットアップします。</span><span class="sxs-lookup"><span data-stu-id="52260-103">Use the contents of the distribution folder to setup the Web service on a destination computer.</span></span>  
  
### <a name="to-install-the-web-setup-package"></a><span data-ttu-id="52260-104">Web セットアップ パッケージをインストールするには</span><span class="sxs-lookup"><span data-stu-id="52260-104">To install the Web setup package</span></span>  
  
1.  <span data-ttu-id="52260-105">セットアップ先コンピューターに配布フォルダをコピーします。</span><span class="sxs-lookup"><span data-stu-id="52260-105">Copy the distribution folder onto the destination computer.</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="52260-106">対象のコンピューターは、BizTalk Server ランタイムをインストールし、必要な BizTalk アセンブリを展開し、グローバル アセンブリ キャッシュにインストールが必要です。</span><span class="sxs-lookup"><span data-stu-id="52260-106">The destination computer must have the BizTalk Server runtime installed and the necessary BizTalk assemblies deployed and installed in the global assembly cache.</span></span>  
  
2.  <span data-ttu-id="52260-107">実行します。Web サービスをインストールし、セットアップ ウィザードの指示に従ってする MSI ファイルには次のメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="52260-107">Run the .MSI file to install the Web service and follow the setup wizard prompts.</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="52260-108">仮想ディレクトリのウィザードで入力するときに、"_Setup"サフィックスを削除します。サフィックスを削除すると、受信場所のアドレスが Web サービスの .asmx ファイルと一致するようにします。</span><span class="sxs-lookup"><span data-stu-id="52260-108">Remove the "_Setup" suffix when the wizard prompts you for the virtual directory.Removing the suffix ensures that the receive location addresses match the Web service .asmx files.</span></span>  
  
3.  <span data-ttu-id="52260-109">仮想ディレクトリのセキュリティ設定が承認に対して正しいことを確認します。</span><span class="sxs-lookup"><span data-stu-id="52260-109">Verify that the security settings for the virtual directory are correct for authorization.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="52260-110">参照</span><span class="sxs-lookup"><span data-stu-id="52260-110">See Also</span></span>  
 [<span data-ttu-id="52260-111">Visual Studio がインストールされていないコンピューターへの公開済み Web サービスの展開</span><span class="sxs-lookup"><span data-stu-id="52260-111">Deploying Published Web Services on a Non-Visual Studio Computer</span></span>](../core/deploying-published-web-services-on-a-non-visual-studio-computer.md)