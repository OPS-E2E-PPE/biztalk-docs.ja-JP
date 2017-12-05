---
title: "ログ ストアの選択 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- configuring, auditing
- configuring, logging
- logging, configuring
- auditing, configuring
ms.assetid: 6ba64c59-3a15-4c10-b44f-18e0e432c6d3
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0518b536db16d641b77a61cfeb4851990a7bca0a
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
---
# <a name="selecting-the-logging-store"></a>ログ ストアを選択します。
[!INCLUDE[btsCoName](../../includes/btsconame-md.md)][!INCLUDE[HL7_CurrentVersion_FirstRef](../../includes/hl7-currentversion-firstref-md.md)]など、さまざまなログ ストアの組み合わせを選択するオプションを使用して提供する[!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)]Management Instrumentation (WMI)、 [!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)]、および[!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)]イベント ログです。  
  
 使用する、[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]ログ ストアを構成するエクスプ ローラーを構成します。  
  
 開くには、次の手順を使用して[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]構成エクスプ ローラーと、ログ ストアを選択します。  
  
### <a name="to-open-btahl7-configuration-explorer"></a>BTAHL7 構成エクスプ ローラーを開く  
  
-   をクリックして**開始**、 をクリックして**プログラム**、 をクリックして**Microsoft BizTalk\<バージョン\>Accelerator 用 HL7**、クリックして**BTAHL7 構成エクスプ ローラー**です。  
  
### <a name="to-select-the--logging-store"></a>ログ ストアを選択  
  
1.  [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]構成エクスプ ローラーで、**グローバル設定** タブで、次の操作します。  
  
    |プロパティ|目的|  
    |--------------|----------------|  
    |**WMI**|BTAHL7 の WMI 通知を生成する場合は、このオプションを選択します。|  
    |**SQL**|使用する場合は、このオプションを選択[!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)]ログ ストアとして。 **注:** BTAHL7 が存在しない場合は、ログに必要なテーブルを自動的に作成します。|  
    |**SQL Server**|型、[!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)]名。 これは、選択したときに必要な**SQL**オプション。 許容最大長は、64 文字です。<br /><br /> 既定のサーバーとデータベース名は、構成された BTAHL7 データベースです。|  
    |**データベース名**|型、[!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)]データベース名。 これは、選択したときに必要な**SQL**オプション。 許容最大長は、128 文字です。|  
    |**イベント ログ**|使用する場合は、このオプションを選択、[!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)]ログ ストアとしてのイベント ログです。 使用する、[!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)]イベント メッセージを表示するイベント ビューアー。|  
  
2.  **[保存]**をクリックします。  
  
    > [!NOTE]
    >  ログ記録イベント ブローカーによって記録されたイベントのロケールは、ログ記録のサービス アカウントのロケールに依存します。  
  
    > [!NOTE]
    >  パスワードを変更する必要があります最初、ログ記録のサービス アカウントのパスワードを変更するときに[!INCLUDE[btsCoName](../../includes/btsconame-md.md)][!INCLUDE[btsAD](../../includes/btsad-md.md)]ディレクトリ サービス、および実行するすべてのサーバーでログ サービスのパスワードを変更した後、ログ記録がサービスを再起動します。  
  
## <a name="see-also"></a>参照  
 [メッセージのバッチ処理](../../adapters-and-accelerators/accelerator-hl7/message-batching.md)   
 [ログ記録の構成](../../adapters-and-accelerators/accelerator-hl7/logging-configuration.md)