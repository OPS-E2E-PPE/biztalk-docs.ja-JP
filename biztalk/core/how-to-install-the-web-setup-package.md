---
title: "Web セットアップ パッケージをインストールする方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- deploying, Web services
- Web services, deploying
- Web services, installing
ms.assetid: c6b38a2f-ad07-4ccd-b267-9e3510df88c3
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 21fbacd76598a3a86cfa70b4761bc74420afe561
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-install-the-web-setup-package"></a>Web セットアップ パッケージをインストールする方法
送信先コンピュータで Web サービスをセットアップするには、配布フォルダの内容を使用します。  
  
### <a name="to-install-the-web-setup-package"></a>Web セットアップ パッケージをインストールするには  
  
1.  セットアップ先コンピューターに配布フォルダにコピーします。  
  
    > [!IMPORTANT]
    >  送信先コンピュータには、BizTalk Server ランタイムがインストールされ、グローバル アセンブリ キャッシュに必要な BizTalk アセンブリが展開されてインストールされていることが必要です。  
  
2.  .MSI ファイルを実行して Web サービスをインストールし、セットアップ ウィザードの指示に従って操作します。  
  
    > [!IMPORTANT]
    >  ウィザードで仮想ディレクトリについて確認するメッセージが表示されたら、"_Setup" サフィックスを削除します。サフィックスを削除することで、確実に受信場所のアドレスが Web サービスの .asmx ファイルと一致するようになります。  
  
3.  仮想ディレクトリのセキュリティ設定が正しく、認証に使用できることを確認します。  
  
## <a name="see-also"></a>参照  
 [非 Visual Studio コンピューターに公開された Web サービスを展開します。](../core/deploying-published-web-services-on-a-non-visual-studio-computer.md)