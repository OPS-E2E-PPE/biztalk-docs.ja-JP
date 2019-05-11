---
title: BizTalk Server の構成をバックアップする方法 |Microsoft Docs
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
ms.openlocfilehash: 9da0d382752a7f3469a8f10a3f2550b06fe84bcb
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65342654"
---
# <a name="how-to-back-up-the-biztalk-server-configuration"></a>BizTalk Server の構成をバックアップする方法
バックアップ処理の一環として[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]、実行しているコンピューターに関連付けられている構成設定をバックアップする必要があります[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]します。 コンピューターを交換する必要があるハードウェア障害がある場合、元の構成ファイルのコピーを大幅にも、復元プロセスが簡略化します。  
  
 実行する各コンピューターの構成設定[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]BizTalk Server 構成マネージャーで作成された XML ファイルに格納されます。 いつでも、BizTalk server の構成を変更するバックアップの場所に更新された構成ファイルをエクスポートする必要があります。 これにより、構成ファイルが、BizTalk server を交換する必要がある場合に使用できることを確認します。  
  
## <a name="prerequisites"></a>前提条件  
 この手順を実行する BizTalk Server 管理者グループのメンバーとしてログオンする必要があります。  
  
### <a name="to-back-up-the-biztalk-server-configuration"></a>BizTalk Server 構成をバックアップするには  
  
1.  クリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして**Microsoft BizTalk Server**、順にクリックします**BizTalk Server 構成**します。  
  
2.  **Microsoft BizTalk Server 構成**、 をクリックして**構成のエクスポート**します。  
  
3.  **付けて** ダイアログ ボックスで、バックアップを保存する場所を参照します。  
  
4.  **ファイル名**ボックスで、構成ファイルの名前を入力し、クリックして**保存**します。  
  
## <a name="see-also"></a>参照  
 [BizTalk Server を実行しているコンピューターのバックアップ](../core/backing-up-a-computer-running-biztalk-server.md)   
 [BizTalk Server の構成を回復する方法](../core/how-to-recover-the-biztalk-server-configuration.md)