---
title: Oracle データベース アダプターのパフォーマンスに関するトラブルシューティング |Microsoft ドキュメント
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
ms.openlocfilehash: 9ba487bcd5d6d245c979dec903613465ae54f8d9
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
ms.locfileid: "25962352"
---
# <a name="troubleshoot-performance-issues-with-the-oracle-database-adapter"></a>Oracle データベース アダプターのパフォーマンスに関するをトラブルシューティングします。
このセクションで説明を使用する場合に発生する可能性があるパフォーマンスの問題を解決するのには、トラブルシューティングの手法を使用して[!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)]です。  
  
## <a name="known-issue"></a>既知の問題  
 使用する場合に発生する可能性が最も一般的なパフォーマンスの問題を次に示します、 [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]、およびその考えられる原因と解決します。  
  
##  <a name="BKMK_Slowdown"></a>処理速度が低下またはスループットのアダプターを BizTalk Server を使用すると停止  
 **問題**  
  
 使用する場合、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]で[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]、アダプターによって送信または受信メッセージの数が遅くなったり、stall にします。  
  
 **原因**  
  
 **EnableBizTalkCompatibilityMode** binding プロパティが設定されていない Wcf-custom 送信ポートまたは受信ポートを BizTalk Server 管理コンソールでします。  
  
 **解決策**  
  
 設定、 **EnableBizTalkCompatibilityMode**バインディング プロパティを True に設定します。 このプロパティの詳細については、次を参照してください。 [Oracle データベース アダプターのバインドのプロパティについてお読み](../../adapters-and-accelerators/adapter-oracle-database/read-about-the-oracle-database-adapter-binding-properties.md)です。 バインディング プロパティを設定する方法の手順については、次を参照してください。 [Oracle データベースのバインドのプロパティを構成する](../../adapters-and-accelerators/adapter-oracle-database/configure-the-binding-properties-for-oracle-database.md)です。  
  
### <a name="possible-memory-leak-on-a-64-bit-computer-when-using-the-oracle-database-adapter-to-perform-operations-involving-float-data-type"></a>Oracle データベース アダプターを使用して、FLOAT データ型に関連する操作を実行する場合に、64 ビット コンピューターにメモリ リーク  
 **問題**  
  
 使用する場合に、メモリ リークが発生する可能性があります、 [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] FLOAT データ型に関連する操作を実行する 64 ビット コンピューターにします。  
  
 **解決策**  
  
 .NET インストール\<*バージョン*\> (x64) 64 ビット コンピューターにします。  
  
## <a name="see-also"></a>参照  
[Oracle のトラブルシューティングを行うデータベース adapter.md](../../adapters-and-accelerators/adapter-oracle-database/troubleshoot-the-oracle-database-adapter.md)