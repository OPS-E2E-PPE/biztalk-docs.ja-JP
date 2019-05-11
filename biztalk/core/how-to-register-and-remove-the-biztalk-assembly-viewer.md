---
title: 登録および BizTalk アセンブリ ビューアーを削除する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 6f80b906-0a9e-4bcd-984d-db4550f2e51f
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8b78aeb8f0ebdbc1a7e05c8cfc45137b991b6eb5
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65384392"
---
# <a name="how-to-register-and-remove-the-biztalk-assembly-viewer"></a>BizTalk アセンブリ ビューアーを登録および削除する方法
BizTalk アセンブリ ビューアーは、BizTalk Server のセットアップ中に自動的に登録されていません。 BizTalk アセンブリ ビューアーを削除または登録は、次の手順に従います。  
  
### <a name="to-add-assembly-viewer-to-the-windows-registry"></a>Windows レジストリにアセンブリ ビューアーを追加するには  
  
1.  **開始** メニューのをクリックして**実行**します。  
  
2.  [実行] ダイアログ ボックスで、入力**cmd**します。  
  
3.  移動しますからコマンド ラインで\< *BizTalk Server のインストール フォルダー*\>\Developer Tools\ BTSAsmExt.dll があります。  
  
4.  コマンドラインで、次のように入力します。  
  
     regsvr32 BTSAsmExt.dll  
  
5.  アセンブリ ビューを使用するには、ログオフしてログオンし、コンピューターに戻すにします。  
  
### <a name="to-remove-assembly-viewer-from-the-windows-registry"></a>Windows レジストリからアセンブリ ビューアーを削除するには  
  
1.  **開始** メニューのをクリックして**実行**します。  
  
2.  **実行**ダイアログ ボックスに「 **cmd**します。  
  
3.  移動しますからコマンド ラインで\< *BizTalk Server のインストール フォルダー*\>\Developer Tools\ BTSAsmExt.dll があります。  
  
4.  コマンドラインで、次のように入力します。  
  
     regsvr32/u BTSAsmExt.dll  
  
5.  削除を完了するには、ログオフしてログオンし、コンピューターに戻すにします。  
  
## <a name="see-also"></a>参照  
 [BizTalk アセンブリ ビューアーを使用したアセンブリの表示](../core/viewing-assemblies-with-the-biztalk-assembly-viewer.md)