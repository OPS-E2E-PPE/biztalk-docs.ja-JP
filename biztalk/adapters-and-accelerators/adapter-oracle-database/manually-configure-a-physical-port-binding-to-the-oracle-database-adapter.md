---
title: Oracle データベース アダプターを物理ポートのバインドを手動で構成 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- messages, sending to an Oracle database
- messages, receiving from an Oracle database
- physical port binding, manually configuring
ms.assetid: 6b118236-e9eb-494e-96b2-969c7064943d
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d2a64223485cf83fb214055cb1e11b44fb6bc7c4
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22214282"
---
# <a name="manually-configure-a-physical-port-binding-to-the-oracle-database-adapter"></a>Oracle データベース アダプターを物理ポートのバインドを手動で構成します。
このセクションの構成に関する情報を提供する、 [!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)] Wcf-oracledb バインディングを使用して、WCF カスタム バインドとして、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソールです。 アダプターを展開したらことができますを使用しての Oracle データベースからメッセージを送受信する、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソールです。 アダプタの展開の手順が異なります。  
  
-   BizTalk Server の間の通信の方向と[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]です。 送信、受信、送信と受信ポートまたは受信と送信ポートを構成することができます。 選択した内容は、次の表にまとめたものです。  
  
    |ポートの方向|通信方式|選択への通信方向|  
    |--------------------|---------------------------|-----------------------------------------------|  
    |Send|一方向|常にこのポートでメッセージを送信します。|  
    |Receive|一方向|常にこのポートでメッセージを受信します。|  
    |送受信|要求 - 応答|要求の送信と応答の受信をされます。|  
    |受信送信|送信請求 - 応答送信アダプター|要求の受信と応答の送信を行います。|  
  
     詳細については、次を参照してください。[送信ポートを作成](../../core/how-to-create-a-send-port2.md)、または[受信ポートを作成](../../core/how-to-create-a-receive-port.md)です。 
  
-   かどうか、アダプターは、Oracle データベースにメッセージを送信または Oracle データベースからメッセージを受信します。 送信またはメッセージを受信するかどうかは、によってを作成、送信または受信ポートをそれぞれします。  
  
    > [!NOTE]
    >  また、送信構成またはによって作成されるバインディングの構成ファイルをインポートしてポートを受信する、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]メタデータの生成の一部として。 このバインド ファイルを使用するポートを構成する方法の詳細については、次を参照してください。 [Oracle データベースへのポートのバインド ファイルを使用して物理ポートのバインドを構成する](../../adapters-and-accelerators/adapter-oracle-database/configure-a-physical-port-binding-using-a-port-binding-file-to-oracle-database.md)です。  
  
 
  
## <a name="see-also"></a>参照  
[BizTalk アプリケーションを開発します。](../../core/develop-your-biztalk-applications.md)