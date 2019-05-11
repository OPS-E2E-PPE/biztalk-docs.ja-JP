---
title: Oracle データベース アダプターのパフォーマンスの問題のトラブルシューティング |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- performance issues, troubleshooting
- troubleshooting, performance issues
ms.assetid: 2035cd2e-ce87-419b-aada-61d257671623
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 23c36e2df514f6caf5e654a99c4d57a5c4b41e65
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65375903"
---
# <a name="troubleshoot-performance-issues-with-the-oracle-database-adapter"></a>Oracle データベース アダプターのパフォーマンスの問題をトラブルシューティングします。
このセクションを使用する場合に発生する可能性のあるパフォーマンスの問題を解決するのには、トラブルシューティングの手法を使用して説明します[!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)]します。  
  
## <a name="known-issue"></a>既知の問題  
 使用する場合に発生する可能性が最も一般的なパフォーマンスの問題を次に、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]と共にその考えられる原因と解決します。  
  
##  <a name="BKMK_Slowdown"></a> 速度低下またはスループットのアダプターを BizTalk Server を使用すると停止  
 **問題**  
  
 使用する場合、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]で[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]、アダプターによって送信または受信メッセージの数が遅くなったり、停止します。  
  
 **原因**  
  
 **EnableBizTalkCompatibilityMode**プロパティのバインドが設定されておらず、Wcf-custom 送信ポートまたは受信ポートを BizTalk Server 管理コンソールでします。  
  
 **解決方法**  
  
 設定、 **EnableBizTalkCompatibilityMode**プロパティを True にバインドします。 このプロパティの詳細については、次を参照してください。 [Oracle データベース アダプターのバインドのプロパティについて](../../adapters-and-accelerators/adapter-oracle-database/read-about-the-oracle-database-adapter-binding-properties.md)します。 バインドのプロパティを設定する方法については、次を参照してください。 [for Oracle Database バインド プロパティを構成する](../../adapters-and-accelerators/adapter-oracle-database/configure-the-binding-properties-for-oracle-database.md)します。  
  
### <a name="possible-memory-leak-on-a-64-bit-computer-when-using-the-oracle-database-adapter-to-perform-operations-involving-float-data-type"></a>FLOAT データ型に関連する操作を実行する Oracle データベース アダプターを使用する場合は、64 ビット コンピューターでメモリ リーク  
 **問題**  
  
 使用する場合にメモリ リークが発生する可能性があります、 [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] FLOAT データ型に関連する操作を実行する 64 ビット コンピューターにします。  
  
 **解決方法**  
  
 .NET インストール\<*バージョン*\> (x64) 64 ビット コンピューターにします。  
  
## <a name="see-also"></a>参照  
[Oracle のトラブルシューティングを行うデータベース adapter.md](../../adapters-and-accelerators/adapter-oracle-database/troubleshoot-the-oracle-database-adapter.md)