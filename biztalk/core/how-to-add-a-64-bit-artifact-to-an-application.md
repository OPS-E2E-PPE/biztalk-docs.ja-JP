---
title: "アプリケーションを 64 ビット アイテムを追加する方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- artifacts, 64-bit support
- scripts, 64-bit support
- virtual directories, 64-bit support
- artifacts, applications
- 64-bit support, COM components
- 64-bit support, virtual directories
- applications, artifacts
- 64-bit support, scripts
- 64-bit support, artifacts
- COM components, 64-bit support
- BizTalk Server, 64-bit support
- applications, 64-bit support
ms.assetid: 46aca7d4-c5be-421e-b16d-7f3095c8cc67
caps.latest.revision: "24"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 69707401fee8b7f48b30a79bab166a9f22c29a89
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-add-a-64-bit-artifact-to-an-application"></a>64 ビット アイテムをアプリケーションに追加する方法
[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] では、64 ビット アプリケーションもサポートされます。 つまり、32 ビット アイテムと同じ方法で 64 ビット アイテムを BizTalk アプリケーションに追加できます。ただし、次の 64 ビット アイテムを 32 ビットのコンピューターにインストールすると次のような問題が発生する場合があります。  
  
-   **64 ビット ワーカー プロセスを実行している Web サーバーから仮想ディレクトリです。** 仮想ディレクトリは 32 ビット コンピューターにインストールされますが、正常に機能しない場合があります。 不一致がログに記録されます。  
  
-   **アンマネージ COM コンポーネントまたはマネージ COM + コンポーネントは、64 ビットとしてマークされます。** これらのコンポーネントは、32 ビット コンピューターにはインストールされません。  
  
-   **64 ビット スクリプトが .exe ファイルとして保存します。** この種類のスクリプトは正常に機能しない場合があります。  
  
 アイテムの追加の一般的な手順については、次を参照してください。[成果物を追加または作成する方法](../core/how-to-create-or-add-an-artifact.md)です。 特定種類のアイテムを追加する方法の詳細については、次を参照してください。[成果物の管理](../core/managing-artifacts.md)です。  
  
## <a name="see-also"></a>参照  
 [作成して、BizTalk アプリケーションの変更](../core/creating-and-modifying-biztalk-applications.md)   
 [BizTalk アプリケーションをインストールする方法](../core/how-to-install-a-biztalk-application.md)