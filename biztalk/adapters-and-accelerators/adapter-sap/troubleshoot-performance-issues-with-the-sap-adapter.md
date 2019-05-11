---
title: SAP アダプターを使用したパフォーマンスの問題のトラブルシューティング |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- troubleshooting, performance
- performance, troubleshooting
ms.assetid: 7e8e9fec-0edf-4c67-837c-0e271b2ffe68
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c44bf56f73cd23de36e53ae6f0720d863e4f694e
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65372387"
---
# <a name="troubleshoot-performance-issues-with-the-sap-adapter"></a>SAP アダプターを使用したパフォーマンスの問題をトラブルシューティングします。
このセクションを使用する場合に発生する可能性のあるパフォーマンスの問題を解決するのには、トラブルシューティングの手法を使用して説明します[!INCLUDE[adaptersap](../../includes/adaptersap-md.md)]します。  
  
##  <a name="BKMK_SAPSlowdown"></a> 速度低下またはスループットのアダプターを BizTalk Server を使用すると停止  
 **問題**  
  
 使用する場合、[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]で[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]、アダプターによって送信または受信メッセージの数が遅くなったり、停止します。  
  
 **原因**  
  
 **EnableBizTalkCompatibilityMode**プロパティのバインドが設定されておらず、Wcf-custom 送信ポートまたは受信ポートを BizTalk Server 管理コンソールでします。  
  
 **解決方法**  
  
 設定、 **EnableBizTalkCompatibilityMode**プロパティを True にバインドします。 このプロパティの詳細については、次を参照してください。 [mySAP Business Suite のバインドのプロパティの BizTalk アダプターについて](../../adapters-and-accelerators/adapter-sap/read-about-biztalk-adapter-for-mysap-business-suite-binding-properties.md)します。 バインドのプロパティを設定する方法については、次を参照してください。 [SAP アダプターのバインドのプロパティを構成する](../../adapters-and-accelerators/adapter-sap/configure-the-binding-properties-for-the-sap-adapter.md)します。  
  
##  <a name="BKMK_SAPMemLeak"></a> パラメーターを NULL 値を使用する場合、メモリ リーク  
 **問題**  
  
 メモリ リークが発生する場合は、SAP システム内の成果物の呼び出し中に入力、またはテーブル パラメーターの値を指定しないを確認できます。  
  
 **解決方法**  
  
 SAP システムで成果物の呼び出し中にすべての入力および表のパラメーターの値を指定することを確認します。  
  
## <a name="see-also"></a>参照  
[SAP アダプターをトラブルシューティングします。](../../adapters-and-accelerators/adapter-sap/troubleshoot-the-sap-adapter.md)