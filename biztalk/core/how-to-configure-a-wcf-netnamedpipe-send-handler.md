---
title: Wcf-netnamedpipe 送信ハンドラーを構成する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- WCF-NetNamedPipe adapters, global adapters
- configuring [WCF-NetNamedPipe adapters], global adapters
- send handlers, WCF-NetNamedPipe adapters
- configuring [WCF-NetNamedPipe adapters], send handlers
ms.assetid: 1f281649-d09f-44eb-8af5-1f83233fab60
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 69941385bdadc3670a88fd48c37fb77e22657752
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65342215"
---
# <a name="how-to-configure-a-wcf-netnamedpipe-send-handler"></a>WCF-NetNamedPipe 送信ハンドラーを構成する方法
送信ハンドラーを Wcf-netnamedpipe を構成するのには、次の手順を使用します。  

### <a name="to-change-global-variables-for-a-wcf-netnamedpipe-send-handler"></a>グローバル変数を Wcf-netnamedpipe 送信ハンドラーを変更するには  

1. BizTalk Server 管理コンソールで  [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)] **管理**、展開**BizTalk グループ**、展開**プラットフォームの設定**順に展開**アダプター**します。  

2. 展開したアダプターの一覧でクリックして**Wcf-netnamedpipe**、右側のウィンドウで、構成する送信ハンドラーを右クリックし をクリック、**プロパティ**します。  

3. **アダプター ハンドラーのプロパティ** ダイアログ ボックスの 、**全般** タブで、**ホスト名**一覧で、送信ハンドラーが関連付けられているが、ホストを選択します。  

4. **全般**] タブで [**プロパティ**します。 **送信ハンドラー**  タブで、次の操作を行います。  


   |        プロパティ         |                                                                                                                                                                                                                                                                             目的                                                                                                                                                                                                                                                                             |
   |-------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
   | **接続の最大数** | 接続プールにキャッシュされている各エンドポイントの発信接続の最大数を指定します。 これによって、一意のリモート エンドポイントのそれぞれに対してキャッシュされる接続数が制限されます。 この値は、一意のリモート エンドポイントに対してキャッシュされることを想定している最大接続数よりも大きい値に設定する必要があります。 アクティブな発信接続の数を超える場合、この最大値、サービスは、この送信ハンドラーで実行されている Wcf-netnamedpipe 送信ポートに応答しないように見える場合があります。<br /><br /> 既定値は 10 です。 |


5. **[OK]** をクリックします。  

## <a name="see-also"></a>参照  
 [WCF サービスの使用](../core/consuming-wcf-services.md)   
 [WCF-NetNamedPipe アダプターの構成](../core/configuring-the-wcf-netnamedpipe-adapter.md)