---
title: "配置時にファイルのアイテムの状態 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- artifacts, status
- deploying [artifacts], status
ms.assetid: 6d0f7336-c2cb-4aa4-9f1d-55fb85fe78bf
caps.latest.revision: "15"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a1f57716741bb61c7a9f6f012aed14ec04c8e250
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="status-of-file-artifacts-during-deployment"></a>展開中のファイル アイテムの状態
処理前または処理後のスクリプトの実行時に、ファイル システム上にどのようなファイルベースのアイテムが存在するかを知ることが必要な場合があります。 たとえば、アンインストール時に処理後のスクリプトを実行して、特定のアイテム ファイルをファイル システムから削除する場合です。 ファイルベースのアイテムは、BizTalk データベース内の表現に加えて、ローカル ファイル システムにもファイルとして存在することができるアイテムです。 ファイルベースのアイテムの例としては、COM コンポーネント、.NET アセンブリ、BizTalk アセンブリ、BAM アイテム、アドホック ファイル、スクリプト、およびバインド ファイルが挙げられます。  
  
 次の表は、展開プロセスの各時点における、アイテム ファイルの状態をまとめたものです。  
  
|展開プロセスの時点|アプリケーション アイテム ファイルの状態|  
|-------------------------------------|------------------------------------------|  
|インストール前|ローカル ファイル システムには、種類が System.BizTalk.File であるファイルだけが存在します。*|  
|インストール後|ローカル ファイル システムには、すべてのファイルが存在します。*|  
|アンインストール前|ローカル ファイル システムには、すべてのファイルが存在します。*|  
|アンインストール後|ローカル ファイル システムからはすべてのファイルが削除されています。|  
|インポート前|アプリケーションがローカル コンピューターにインストールされていない限り、ローカル ファイル システムにファイルは存在しません。|  
|インポート後|アプリケーションがローカル コンピューターにインストールされていない限り、ローカル ファイル システムにファイルは存在しません。|  
  
 \*ファイルは、有効なコピー先の場所は、ファイルがアプリケーションに追加したときに指定されていた場合にのみ、ローカル ファイル システムに存在します。  
  
## <a name="see-also"></a>参照  
 [前処理および後処理のスクリプトを使用したアプリケーションの展開のカスタマイズ](../core/using-pre-and-post-processing-scripts-to-customize-application-deployment.md)