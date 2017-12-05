---
title: "Rnpip の既存の PIP の変更 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- RNPIPs
- modifying, PIPs
- PIPs, modifying
- assemblies, RNPIPs
ms.assetid: f2ed25c4-1979-4691-9315-e7568e7cca8b
caps.latest.revision: "13"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ce7f87d9af24e6388199e76e9cbf0eba076ceacf
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/01/2017
---
# <a name="modifying-an-existing-pip-in-rnpips"></a>Rnpip の既存の PIP の変更
このトピックを変更し、再デプロイしてインストール プロセス PIP (Partner Interface) スキーマの 1 つの方法について説明[!INCLUDE[btsCoName](../../includes/btsconame-md.md)][!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)]セットアップします。 スキーマは、RNPIP アセンブリの一部として展開します。  
  
### <a name="to-modify-an-existing-pip-in-rnpips"></a>RNPIP の既存の PIP を変更するには  
  
1.  をクリックして**開始**、 をクリックして**実行**、型**cmd**、順にクリック**ok**です。  
  
2.  検索、 \<*ドライブ*\>\Program Files\Microsoft BizTalk\<バージョン\>Accelerator for rosettanet \sdk\utilities\schema Generator フォルダーです。  
  
3.  コマンド プロンプトで次のように入力します。 **CScript InstallDTD.vbs**、ENTER キーを押します。  
  
    > [!NOTE]
    >  のみ、BizTalk Server をインストールした後 1 および 2 の 1 回の手順を実行する必要があります。  
  
4.  開始**Microsoft Visual Studio 2012**です。  
  
5.  **ファイル** メニューのをポイント**開く**、クリックして**プロジェクト**です。  
  
6.  **プロジェクトを開く**] ダイアログ ボックスに移動\<*ドライブ*\>\Program Files\Microsoft BizTalk\<バージョン\>Accelerator for rosettanet \sdk\クリックして、スキーマ**[RNPIPs.btproj**です。  
  
7.  **ビュー**  メニューをクリックして**BizTalk エクスプ ローラー**です。 展開**アセンブリ**、し、右クリックし、 **Microsoft.Solutions.BTARN.Schemas.RNPIPs(3.3.0.0)**です。 をクリックして**展開解除**です。  
  
8.  開始**Visual Studio 2012 コマンド プロンプト**です。  
  
9. コマンド プロンプトで「手順 6. で入力した場所に移動**sn-k RNPIPs.snk**、キーを押します**Enter**です。  
  
10. ソリューション エクスプ ローラーで右クリック**Rnpip**、 をクリックして**プロパティ**、 をクリックして**共通プロパティ**、クリックして**アセンブリ。**  
  
11. 右側のペインで下にスクロール**厳密名**で、**アセンブリ キー ファイル**セクションで、省略記号ボタン ([...]) ボタンをクリックし、コマンド プロンプトで「手順 6. で入力した場所に移動**RNPIPs.snk**、クリックして**OK**です。  
  
12. **プロパティ ページ**ダイアログ ボックスで、をクリックして**構成プロパティ**、 をクリックして**展開**、 をクリックして**再展開**を選択して`True`、クリックして**OK**です。  
  
13. 必要に応じて RNPIP の既存のスキーマを編集します。  
  
14. をクリックして**ファイル**、クリックして**保存**です。  
  
15. プロジェクト名を右クリックし、をクリックして**ビルド**です。  
  
16. プロジェクト名を右クリックし、をクリックして**展開**です。  
  
17. をクリックして**開始**、 をポイント**すべてのプログラム**、 をポイント**Microsoft** [!INCLUDE[btsBizTalkServer2006r3ui](../../includes/btsbiztalkserver2006r3ui-md.md)]、順にクリック**BizTalk Server 管理コンソール**です。  
  
18. BizTalk 管理コンソールで、展開**Microsoft** [!INCLUDE[btsBizTalkServer2006r3ui](../../includes/btsbiztalkserver2006r3ui-md.md)] **(ローカル)**の順に展開および**ホスト**です。  
  
19. 右側のウィンドウで、ホストの名前を右クリックし、をクリックして**停止**です。 サービスが停止した後、ホストの名前を右クリックし、をクリックして**開始**です。  
  
## <a name="see-also"></a>参照  
 [プログラミング ガイド](../../adapters-and-accelerators/accelerator-rosettanet/programming-guide2.md)   
 [新しい Partner Interface Process の組み込み](../../adapters-and-accelerators/accelerator-rosettanet/incorporating-a-new-partner-interface-process.md)