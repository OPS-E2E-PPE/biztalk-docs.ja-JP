---
title: Wcf-nettcp 送信ハンドラーを構成する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- send handlers, WCF-NetTcp adapters
- configuring [WCF-NetTcp adapters], send handlers
- WCF-NetTcp adapters, global variables
- configuring [WCF-NetTcp adapters], global variables
ms.assetid: c60fe03d-7e11-4e08-9a24-8ff443eee9c1
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5855c7405437d7958f53d679ad2eafc670608c7a
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37014107"
---
# <a name="how-to-configure-a-wcf-nettcp-send-handler"></a>WCF-NetTcp 送信ハンドラーを構成する方法
WCF-NetTcp 送信ハンドラーを構成するには、次の手順を使用します。  

### <a name="to-change-global-variables-for-a-wcf-nettcp-send-handler"></a>WCF-NetTcp 送信ハンドラーのグローバル変数を変更するには  

1. BizTalk 管理コンソールで、 [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)] **管理**、展開**BizTalk グループ**、展開**プラットフォームの設定**を展開し**アダプター**します。  

2. 展開したアダプターの一覧でクリックして**Wcf-nettcp**、右側のウィンドウで、構成する送信ハンドラーを右クリックし をクリック、**プロパティ**します。  

3. **アダプター ハンドラーのプロパティ** ダイアログ ボックスの 、**全般** タブで、**ホスト名**一覧で、送信ハンドラーが関連付けられているが、ホストを選択します。  

4. **全般**] タブで [**プロパティ**します。 **送信ハンドラー**  タブで、次の操作を行います。  


   |        プロパティ         |                                                                                                                                                                                                                                                                          目的                                                                                                                                                                                                                                                                          |
   |-------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
   | **接続の最大数** | 接続プール内にキャッシュされている各エンドポイントの最大送信接続数を指定します。 これによって、一意のリモート エンドポイントのそれぞれに対してキャッシュされる接続数が制限されます。 この値は、一意のリモート エンドポイントに対してキャッシュされることを想定している最大接続数よりも大きい値に設定する必要があります。 アクティブな送信接続数がこの最大値を超えると、サービスが、この送信ハンドラーで実行されている WCF-NetTcp 送信ポートに応答していないように見える場合があります。<br /><br /> 既定値は 10 です。 |


5. **[OK]** をクリックします。  

## <a name="see-also"></a>参照  
 [WCF サービスの使用](../core/consuming-wcf-services.md)   
 [WCF-NetTcp アダプターの構成](../core/configuring-the-wcf-nettcp-adapter.md)