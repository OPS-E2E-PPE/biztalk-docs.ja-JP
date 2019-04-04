---
title: アプリケーションを 64 ビット アイテムを追加する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
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
caps.latest.revision: 24
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 979b7be419be6b39c5a80fcd1548af7404588e01
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37012867"
---
# <a name="how-to-add-a-64-bit-artifact-to-an-application"></a>64 ビット アイテムをアプリケーションに追加する方法
[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] では、64 ビット アプリケーションもサポートされます。 つまり、32 ビット アイテムと同じ方法で 64 ビット アイテムを BizTalk アプリケーションに追加できます。ただし、次の 64 ビット アイテムを 32 ビットのコンピューターにインストールすると次のような問題が発生する場合があります。  
  
- **64 ビット ワーカー プロセスを実行している Web サーバーから仮想ディレクトリ。** 仮想ディレクトリは 32 ビット コンピューターにインストールされますが、正常に機能しない場合があります。 不一致がログに記録されます。  
  
- **アンマネージ COM またはマネージ COM + コンポーネントは、64 ビットとしてマークします。** これらのコンポーネントは、32 ビット コンピューターにはインストールされません。  
  
- **64 ビットの .exe ファイルとして保存されたスクリプトです。** この種類のスクリプトは正常に機能しない場合があります。  
  
  成果物を追加する方法の一般的な手順は、[成果物を追加または作成する方法](../core/how-to-create-or-add-an-artifact.md)を参照してください。 特定の成果物の種類を追加する手順については、[管理成果物](../core/managing-artifacts.md)を参照してください。  
  
## <a name="see-also"></a>参照  
 [作成して、BizTalk アプリケーションの変更](../core/creating-and-modifying-biztalk-applications.md)   
 [BizTalk アプリケーションをインストールする方法](../core/how-to-install-a-biztalk-application.md)