---
title: "BTSTask のコンソールの色を編集する方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 725dcb7b-5a19-4166-9d1c-93f30ddca201
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0d68529f01ab8131739d735ad82d804b41a9c021
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-edit-the-console-colors-for-btstask"></a>BTSTask のコンソールの色を編集する方法
ここでは、BTSTask がコンソールに出力する際に使用される前景色の編集方法について説明します。 コンソールの背景色が白だと、既定の BTSTask コンソールの出力が読みづらくなってしまうため、前景色の変更が必要になります。  
  
## <a name="prerequisites"></a>前提条件  
 このトピックの手順を実行するには、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] インストール フォルダーに格納されている BTSTask.exe.config ファイルに対する読み取り/書き込みアクセス許可が必要です。  
  
### <a name="to-edit-the-console-foreground-colors-for-btstask"></a>BTSTask のコンソールの前景色を編集するには  
  
1.  BTSTask を実行するコンピューターから、[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]、テキスト エディター、または XML エディターを使用して、BTSTask.exe.config を開きます。 このファイルは、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] のインストール フォルダーに格納されています。  
  
2.  エラー メッセージ、警告、情報など、各種のコンソール出力に使用する前景色に応じて、Console.ForegroundColor.Error、Console.ForegroundColor.Warning、Console.ForegroundColor.Info の各キーの値を編集し、ファイルを保存します。 (モノクロの場合は、値を編集するのではなく、これらの 3 つのエントリを削除してください。)  
  
     前景色に使用できる値は次のとおりです。  
  
     0: 黒  
  
     1: DarkBlue  
  
     2: DarkGreen  
  
     3: DarkCyan  
  
     4: DarkRed  
  
     5: DarkMagenta  
  
     6: DarkYellow  
  
     7: 灰色  
  
     8: DarkGray  
  
     9: 青  
  
     10: 緑  
  
     11: シアン  
  
     12: 赤  
  
     13: マゼンタ  
  
     14: 黄色  
  
     15: 白  
  
## <a name="see-also"></a>参照  
 [BTSTask コマンド ライン リファレンス](../core/btstask-command-line-reference.md)