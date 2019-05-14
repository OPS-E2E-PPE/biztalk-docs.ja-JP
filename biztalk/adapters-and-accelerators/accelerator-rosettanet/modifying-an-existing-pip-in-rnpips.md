---
title: Rnpip の既存の PIP の変更 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- RNPIPs
- modifying, PIPs
- PIPs, modifying
- assemblies, RNPIPs
ms.assetid: f2ed25c4-1979-4691-9315-e7568e7cca8b
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c9f7b7bf3f3095e5ac1f5bc87b730935de70d63e
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65282916"
---
# <a name="modifying-an-existing-pip-in-rnpips"></a>Rnpip の既存の PIP の変更
このトピックでは、変更し、Microsoft がインストールされているパートナー インターフェイス Process (PIP) スキーマの 1 つを再デプロイする方法を説明します[!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)]セットアップします。 Rnpip アセンブリの一部としてスキーマを展開するとします。  
  
### <a name="to-modify-an-existing-pip-in-rnpips"></a>Rnpip の既存の PIP を変更するには  
  
1. をクリックして**開始**、 をクリックして**実行**、型**cmd**、順にクリックします**OK**。  
  
2. 検索、 \<*ドライブ*\>\Program Files\Microsoft BizTalk\<バージョン\>Accelerator for rosettanet \sdk\utilities\schema Generator フォルダーに移動します。  
  
3. コマンド プロンプトで「 **CScript InstallDTD.vbs**し、ENTER キーを押します。  
  
   > [!NOTE]
   >  のみ、BizTalk Server をインストールした後 1 と 2 つの 1 回の手順を実行する必要があります。  
  
4. 開始**Microsoft Visual Studio 2012**します。  
  
5. **ファイル**メニューで、**オープン**、 をクリックし、**プロジェクト**します。  
  
6. **プロジェクトを開く** ダイアログ ボックスに移動\<*ドライブ*\>\Program Files\Microsoft BizTalk\<バージョン\>Accelerator for rosettanet \sdk\スキーマ、および選択**RNPIPs.btproj**します。  
  
7. **ビュー**  メニューのをクリックして**BizTalk エクスプ ローラー**します。 展開**アセンブリ**、右クリックし、 **Microsoft.Solutions.BTARN.Schemas.RNPIPs(3.3.0.0)** します。 クリックして**展開解除**します。  
  
8. 開始**Visual Studio 2012 のコマンド プロンプト**します。  
  
9. 型であるコマンド プロンプトで、手順 6. で入力した場所に移動**sn-k RNPIPs.snk**、し、キーを押します**Enter**します。  
  
10. ソリューション エクスプ ローラーで右クリックして**Rnpip**、 をクリックして**プロパティ**、 をクリックして**共通プロパティ**、 をクリックし、**アセンブリ。**  
  
11. 右側のペインでスクロールして**厳密な名前**の**アセンブリ キー ファイル**セクションで、省略記号ボタン (…) ボタンをクリックして、型、コマンド プロンプトで、手順 6. で入力した場所に移動**RNPIPs.snk**、 をクリックし、 **OK**します。  
  
12. **プロパティ ページ**ダイアログ ボックスで、をクリックして**構成プロパティ**、 をクリックして**展開**、 をクリックして**再デプロイ**を選択します`True`。、 をクリックし、 **OK**します。  
  
13. 必要に応じてで Rnpip の既存のスキーマのいずれかを編集します。  
  
14. クリックして**ファイル**、 をクリックし、**保存**します。  
  
15. プロジェクト名を右クリックし、**ビルド**します。  
  
16. プロジェクト名を右クリックし、**デプロイ**します。  
  
17. **[スタート]** ボタンをクリックして、 **[すべてのプログラム]**、 **Microsoft**** [!INCLUDE[btsBizTalkServer2006r3ui](../../includes/btsbiztalkserver2006r3ui-md.md)]の順にポイントし、 **[BizTalk Server 管理]** をクリックします。  
  
18. BizTalk 管理コンソールで  **Microsoft** [!INCLUDE[btsBizTalkServer2006r3ui](../../includes/btsbiztalkserver2006r3ui-md.md)] **(Local)**、順に展開**ホスト**します。  
  
19. 右側のウィンドウで、ホストの名前を右クリックし をクリックし、**停止**します。 サービスが停止したら、ホストの名前を右クリックし をクリックし、**開始**します。  
  
## <a name="see-also"></a>参照  
 [プログラミング ガイド](../../adapters-and-accelerators/accelerator-rosettanet/programming-guide2.md)   
 [新しい Partner Interface Process の組み込み](../../adapters-and-accelerators/accelerator-rosettanet/incorporating-a-new-partner-interface-process.md)