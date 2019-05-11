---
title: Oracle データベース アダプターを物理ポートのバインドを手動で構成 |Microsoft Docs
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
ms.openlocfilehash: f67e289044ec10ee3a424e008126a54d381d5180
ms.sourcegitcommit: d27732e569b0897361dfaebca8352aa97bb7efe1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/10/2019
ms.locfileid: "65529046"
---
# <a name="manually-configure-a-physical-port-binding-to-the-oracle-database-adapter"></a>Oracle データベース アダプターを物理ポートのバインドを手動で構成します。
このセクションでは、構成に関する情報を提供、 [!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)] Wcf-oracledb バインドを使用して、WCF カスタム バインドとして、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソール。 アダプターを展開した後はできるを使用しての Oracle データベースからメッセージを送受信する、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソール。 アダプターを展開する手順は、に応じて異なります。  
  
- BizTalk Server 間の通信の方向と[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]します。 送信、受信、送信と受信、または受信送信ポートを構成することができます。 選択内容は、次の表にまとめたものです。  
  
  |ポートの方向|通信方式|選択する通信の方向|  
  |--------------------|---------------------------|-----------------------------------------------|  
  |Send|一方向|常にこのポートでメッセージを送信します。|  
  |Receive|一方向|常にこのポートでメッセージを受信します。|  
  |送受信|要求 - 応答|要求の送信と応答の受信をされます。|  
  |受信送信|送信請求 - 応答送信アダプター|要求の受信と応答の送信を行います。|  
  
   詳細については、次を参照してください。[送信ポートを作成](../../core/how-to-create-a-send-port2.md)、または[受信ポートを作成](../../core/how-to-create-a-receive-port.md)です。 
  
- かどうか、アダプターは、Oracle データベースにメッセージを送信または Oracle データベースからメッセージを受信します。 によって送信またはメッセージを受信するかどうかを作成、送信または受信ポート、それぞれします。  
  
  > [!NOTE]
  >  構成、送信またはによって作成されるバインド構成ファイルをインポートしてポートを受信することができますも、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]メタデータの生成の一部として。 このバインド ファイルを使用してポートを構成する方法の詳細については、次を参照してください。 [Oracle データベースへのポート バインド ファイルを使用して物理的なポート バインドを構成する](../../adapters-and-accelerators/adapter-oracle-database/configure-a-physical-port-binding-using-a-port-binding-file-to-oracle-database.md)します。  
  
 
  
## <a name="see-also"></a>参照  
[BizTalk アプリケーションを開発します。](../../core/develop-your-biztalk-applications.md)