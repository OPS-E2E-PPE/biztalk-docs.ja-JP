---
title: Oracle E-business アダプターを物理ポートのバインドを手動で構成 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 07369428-7b54-4d90-8c63-ba14e67fdbdd
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 354b3937036e9cff832b3c0898ea1fa8d41c6377
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36966683"
---
# <a name="manually-configure-a-physical-port-binding-to-the-oracle-e-business-adapter"></a>Oracle E-business アダプターを物理ポートのバインドを手動で構成します。
このセクションでは、構成に関する情報を提供、 [!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)] WCF カスタム バインドとして、またはを使用して Wcf-oracleebs ポートとして、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソール。 アダプタの展開、できるようになりますを送信してから Oracle E-business Suite を使用してメッセージを受信できるように、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソール。 アダプターを展開する手順は、に応じて異なります。  
  
- 間の通信の方向[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]、[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]します。 送信、受信、送信と受信、または受信送信ポートを構成することができます。 選択内容は、次の表にまとめたものです。  
  
  |ポートの方向|通信方式|選択する通信の方向|  
  |--------------------|---------------------------|-----------------------------------------------|  
  |Send|一方向|常にこのポートでメッセージを送信します。|  
  |Receive|一方向|常にこのポートでメッセージを受信します。|  
  |送受信|要求 - 応答|要求の送信と応答の受信をされます。|  
  |受信送信|送信請求 - 応答送信アダプター|要求の受信と応答の送信を行います。|  
  
   詳細については、次を参照してください。、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]ヘルプ ドキュメントで[ http://go.microsoft.com/fwlink/?LinkID=101130](http://go.microsoft.com/fwlink/?LinkID=101130)します。  
  
- アダプターが送信するかどうかへのメッセージまたは Oracle E-business Suite からメッセージを受信します。 によって送信またはメッセージを受信するかどうかを作成、送信または受信ポート、それぞれします。  
  
  > [!NOTE]
  >  構成、送信またはによって作成されるバインド構成ファイルをインポートしてポートを受信することができますも、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]メタデータの生成の一部として。 このバインド ファイルを使用してポートを構成する方法の詳細については、次を参照してください。 [Oracle E-business Suite へのポート バインド ファイルを、物理ポートを使用してバインディングを構成](../../adapters-and-accelerators/adapter-oracle-ebs/configure-a-physical-port-binding-using-a-port-binding-file-to-oracle-ebs.md)します。  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [Wcf-custom アダプターおよび Oracle E-business Suite を使用してポートを構成します。](../../adapters-and-accelerators/adapter-oracle-ebs/configure-a-port-using-the-wcf-custom-adapter-and-oracle-e-business-suite.md)  
  
-   [Wcf-oracleebs アダプターを使用してポートを構成します。](../../adapters-and-accelerators/adapter-oracle-ebs/configure-a-port-using-the-wcf-oracleebs-adapter.md)  
  
## <a name="see-also"></a>参照  
 [Oracle E-business Suite のアプリケーションを作成する構成要素](../../adapters-and-accelerators/adapter-oracle-ebs/building-blocks-to-create-oracle-e-business-suite-applications.md)