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
# <a name="how-to-install-the-web-setup-package"></a>Web セットアップ パッケージをインストールする方法
配布フォルダの内容を使用して、対象のコンピュータで Web サービスをセットアップします。  
  
### <a name="to-install-the-web-setup-package"></a>Web セットアップ パッケージをインストールするには  
  
1.  セットアップ先コンピューターに配布フォルダをコピーします。  
  
    > [!IMPORTANT]
    >  対象のコンピューターは、BizTalk Server ランタイムをインストールし、必要な BizTalk アセンブリを展開し、グローバル アセンブリ キャッシュにインストールが必要です。  
  
2.  実行します。Web サービスをインストールし、セットアップ ウィザードの指示に従ってする MSI ファイルには次のメッセージが表示されます。  
  
    > [!IMPORTANT]
    >  仮想ディレクトリのウィザードで入力するときに、"_Setup"サフィックスを削除します。サフィックスを削除すると、受信場所のアドレスが Web サービスの .asmx ファイルと一致するようにします。  
  
3.  仮想ディレクトリのセキュリティ設定が承認に対して正しいことを確認します。  
  
## <a name="see-also"></a>参照  
 [Visual Studio がインストールされていないコンピューターへの公開済み Web サービスの展開](../core/deploying-published-web-services-on-a-non-visual-studio-computer.md)