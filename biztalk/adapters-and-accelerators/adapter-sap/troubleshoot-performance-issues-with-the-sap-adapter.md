---
title: "SAP アダプターを使用したパフォーマンスの問題をトラブルシューティング |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- troubleshooting, performance
- performance, troubleshooting
ms.assetid: 7e8e9fec-0edf-4c67-837c-0e271b2ffe68
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ef9e18a2f26af993da36a13d389f2aff2ad2f60a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="troubleshoot-performance-issues-with-the-sap-adapter"></a>SAP アダプターを使用したパフォーマンスの問題をトラブルシューティングします。
このセクションで説明を使用する場合に発生する可能性があるパフォーマンスの問題を解決するのには、トラブルシューティングの手法を使用して[!INCLUDE[adaptersap](../../includes/adaptersap-md.md)]です。  
  
##  <a name="BKMK_SAPSlowdown"></a>処理速度が低下またはスループットのアダプターを BizTalk Server を使用すると停止  
 **問題**  
  
 使用する場合、[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]で[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]、アダプターによって送信または受信メッセージの数が遅くなったり、stall にします。  
  
 **原因**  
  
 **EnableBizTalkCompatibilityMode** binding プロパティが設定されていない Wcf-custom 送信ポートまたは受信ポートを BizTalk Server 管理コンソールでします。  
  
 **解決策**  
  
 設定、 **EnableBizTalkCompatibilityMode**バインディング プロパティを True に設定します。 このプロパティの詳細については、次を参照してください。 [mySAP Business Suite のバインドのプロパティの BizTalk アダプターの説明を読む](../../adapters-and-accelerators/adapter-sap/read-about-biztalk-adapter-for-mysap-business-suite-binding-properties.md)です。 バインディング プロパティを設定する方法の手順については、次を参照してください。 [SAP アダプターのバインドのプロパティを構成する](../../adapters-and-accelerators/adapter-sap/configure-the-binding-properties-for-the-sap-adapter.md)です。  
  
##  <a name="BKMK_SAPMemLeak"></a>パラメーターを NULL 値を使用する場合の可能なメモリ リーク  
 **問題**  
  
 メモリがリークする SAP システム内の成果物の呼び出し中に入力またはテーブルのパラメーターの値を指定しない場合を確認することがあります。  
  
 **解決策**  
  
 SAP システム内の成果物の呼び出し中にすべての入力およびテーブルのパラメーターの値を指定することを確認します。  
  
## <a name="see-also"></a>参照  
[SAP アダプターをトラブルシューティングします。](../../adapters-and-accelerators/adapter-sap/troubleshoot-the-sap-adapter.md)