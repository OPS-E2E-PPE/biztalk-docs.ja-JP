---
title: BizTalk Server の構成をバックアップする方法 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 14f89050-c204-4d44-a875-299e690489ef
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ad54aba8f8f49adeb8534bdbe28add15f0fe9638
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22247658"
---
# <a name="how-to-back-up-the-biztalk-server-configuration"></a>BizTalk Server 構成をバックアップする方法
[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] のバックアップ処理の一環として、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] が実行されているコンピューターに関連付けられた構成設定をバックアップする必要があります。 元の構成ファイルのコピーを保持しておくと、コンピューターの交換が必要になるようなハードウェア障害が発生した場合の復元処理が大幅に簡略化されます。  
  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] が実行されている各コンピューターの構成設定は、BizTalk Server 構成マネージャーによって作成される XML ファイルに格納されます。 BizTalk Server の構成を変更するたびに、更新された構成ファイルをバックアップ先にエクスポートする必要があります。 これにより、BizTalk Server を交換する必要がある場合に、構成ファイルを使用できるようになります。  
  
## <a name="prerequisites"></a>前提条件  
 ここで示す手順を実行するには、BizTalk Server Administrators グループのメンバーとしてログオンする必要があります。  
  
### <a name="to-back-up-the-biztalk-server-configuration"></a>BizTalk Server 構成をバックアップするには  
  
1.  をクリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして**Microsoft BizTalk Server**、順にクリック**BizTalk Server 構成**です。  
  
2.  **Microsoft BizTalk Server 構成**をクリックして**構成のエクスポート**です。  
  
3.  **名前を付けて保存**ダイアログ ボックスで、バックアップを格納する場所を参照します。  
  
4.  **ファイル名**ボックスで、構成ファイルの名前を入力し、をクリックして**保存**です。  
  
## <a name="see-also"></a>参照  
 [BizTalk Server を実行しているコンピューターのバックアップ](../core/backing-up-a-computer-running-biztalk-server.md)   
 [BizTalk Server の構成を回復する方法](../core/how-to-recover-the-biztalk-server-configuration.md)