---
title: "登録および BizTalk アセンブリ ビューアーを削除する方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 6f80b906-0a9e-4bcd-984d-db4550f2e51f
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: deae453be1a89049f223e2da9813e449d68eeb07
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-register-and-remove-the-biztalk-assembly-viewer"></a>BizTalk アセンブリ ビューアーを登録および削除する方法
BizTalk アセンブリ ビューアーは、BizTalk Server のセットアップ時に自動的に登録されません。 BizTalk アセンブリ ビューアーを登録または削除するには、次の手順を実行します。  
  
### <a name="to-add-assembly-viewer-to-the-windows-registry"></a>Windows レジストリにアセンブリ ビューアーを追加するには  
  
1.  **開始** メニューのをクリックして**実行**です。  
  
2.  [実行] ダイアログ ボックスに入力**cmd**です。  
  
3.  コマンド ラインに移動\< *BizTalk Server のインストール フォルダー*> \Developer Tools\ BTSAsmExt.dll があります。  
  
4.  コマンド ラインで、次のコマンドを入力します。  
  
     regsvr32 BTSAsmExt.dll  
  
5.  アセンブリ ビューの使用を開始するには、コンピューターからログオフしてログオンし直します。  
  
### <a name="to-remove-assembly-viewer-from-the-windows-registry"></a>Windows レジストリからアセンブリ ビューアーを削除するには  
  
1.  **開始** メニューのをクリックして**実行**です。  
  
2.  **実行** ダイアログ ボックスで、「 **cmd**です。  
  
3.  コマンド ラインに移動\< *BizTalk Server のインストール フォルダー*> \Developer Tools\ BTSAsmExt.dll があります。  
  
4.  コマンド ラインで、次のコマンドを入力します。  
  
     regsvr32/u BTSAsmExt.dll  
  
5.  削除を完了するには、コンピューターからログオフしてログオンし直します。  
  
## <a name="see-also"></a>参照  
 [BizTalk アセンブリ ビューアーを使用してアセンブリを表示します。](../core/viewing-assemblies-with-the-biztalk-assembly-viewer.md)