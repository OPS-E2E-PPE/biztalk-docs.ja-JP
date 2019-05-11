---
title: BTSTask のコンソールの色を編集する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 725dcb7b-5a19-4166-9d1c-93f30ddca201
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 71d902e18c851d3ae2ae432fa1e39d5db4e75206
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65338076"
---
# <a name="how-to-edit-the-console-colors-for-btstask"></a>BTSTask のコンソールの色を編集する方法
このトピックでは、BTSTask がコンソールに出力する、前景色を編集する方法について説明します。 コンソールの背景色が白の場合、既定の BTSTask コンソールの出力を読むことが困難になり、コンソールの前景色の色を変更する必要があります。  
  
## <a name="prerequisites"></a>前提条件  
 このトピックの手順を実行するに含まれている BTSTask.exe.config ファイルに対する読み取り/書き込みアクセス許可が必要、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]インストール フォルダーです。  
  
### <a name="to-edit-the-console-foreground-colors-for-btstask"></a>BTSTask のコンソールの前景色を編集するには  
  
1. BTSTask を実行するコンピューターで、BTSTask.exe.config を開きます[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]またはテキスト エディターまたは XML エディター。 このファイルにある、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]インストール フォルダーです。  
  
2. に従って必要なエラー メッセージ、警告、およびについては、それぞれ、コンソールの前景の色など、Console.ForegroundColor.Warning、console.foregroundcolor.info のキーの値を編集し、ファイルを保存します。 (モノクロの場合、削除、値を編集するのではなく、これら 3 つのエントリ)。  
  
    前景の色に使用できる値は次のとおりです。  
  
    0:黒  
  
    1:DarkBlue  
  
    2:DarkGreen  
  
    3:DarkCyan  
  
    4:DarkRed  
  
    5:DarkMagenta  
  
    6:DarkYellow  
  
    7:灰色  
  
    8:濃い灰色  
  
    9:[青]  
  
    10:[緑]  
  
    11:シアン  
  
    12:[赤]  
  
    13:赤紫  
  
    14:黄  
  
    15:White  
  
## <a name="see-also"></a>参照  
 [BTSTask コマンド ライン リファレンス](../core/btstask-command-line-reference.md)