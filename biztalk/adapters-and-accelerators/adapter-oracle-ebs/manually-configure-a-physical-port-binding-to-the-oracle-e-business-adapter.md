---
title: Oracle E-business アダプターを物理ポートのバインドを手動で構成 |Microsoft ドキュメント
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
ms.openlocfilehash: 24ea54009ba97732cbcf6f248127b078c1c9ed05
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22216418"
---
# <a name="manually-configure-a-physical-port-binding-to-the-oracle-e-business-adapter"></a>Oracle E-business アダプターを物理ポートのバインドを手動で構成します。
このセクションの構成に関する情報を提供する、 [!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)] WCF カスタム バインドとして、またはを使用して Wcf-oracleebs ポートとして、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソールです。 アダプターを展開したらことができますを使用しての Oracle E-business Suite からメッセージを送受信する、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソールです。 アダプタの展開の手順が異なります。  
  
-   間の通信の方向[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]と[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]です。 送信、受信、送信と受信ポートまたは受信と送信ポートを構成することができます。 選択した内容は、次の表にまとめたものです。  
  
    |ポートの方向|通信方式|選択への通信方向|  
    |--------------------|---------------------------|-----------------------------------------------|  
    |Send|一方向|常にこのポートでメッセージを送信します。|  
    |Receive|一方向|常にこのポートでメッセージを受信します。|  
    |送受信|要求 - 応答|要求の送信と応答の受信をされます。|  
    |受信送信|送信請求 - 応答送信アダプター|要求の受信と応答の送信を行います。|  
  
     詳細については、次を参照してください。、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]ヘルプ ドキュメントで[http://go.microsoft.com/fwlink/?LinkID=101130](http://go.microsoft.com/fwlink/?LinkID=101130)です。  
  
-   アダプターが送信するかどうかへのメッセージまたは Oracle E-business Suite からメッセージを受信します。 送信またはメッセージを受信するかどうかは、によってを作成、送信または受信ポートをそれぞれします。  
  
    > [!NOTE]
    >  また、送信構成またはによって作成されるバインディングの構成ファイルをインポートしてポートを受信する、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]メタデータの生成の一部として。 このバインド ファイルを使用するポートを構成する方法の詳細については、次を参照してください。 [Oracle E-business Suite にポートのバインド ファイルを、物理ポートを使用してバインディングを構成](../../adapters-and-accelerators/adapter-oracle-ebs/configure-a-physical-port-binding-using-a-port-binding-file-to-oracle-ebs.md)です。  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [Wcf-custom アダプターおよび Oracle E-business Suite を使用してポートを構成します。](../../adapters-and-accelerators/adapter-oracle-ebs/configure-a-port-using-the-wcf-custom-adapter-and-oracle-e-business-suite.md)  
  
-   [Wcf-oracleebs アダプターを使用して、ポートの構成](../../adapters-and-accelerators/adapter-oracle-ebs/configure-a-port-using-the-wcf-oracleebs-adapter.md)  
  
## <a name="see-also"></a>参照  
 [Oracle E-business Suite アプリケーションを作成する構成要素](../../adapters-and-accelerators/adapter-oracle-ebs/building-blocks-to-create-oracle-e-business-suite-applications.md)