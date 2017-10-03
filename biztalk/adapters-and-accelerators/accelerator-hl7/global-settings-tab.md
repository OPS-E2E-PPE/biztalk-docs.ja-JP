---
title: "グローバル設定 タブ |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: btahl7.configurationexplorer.tab.globalsettings
helpviewer_keywords:
- configuring, auditing
- configuring, logging
- logging, configuring
- Global Settings tab [Configuration Explorer]
- auditing, configuring
ms.assetid: 057189f7-9072-4841-950f-371ba1f73a15
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 022ad14cc93b55c7ad928c06358f2714531b40b8
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="global-settings-tab"></a>グローバル設定 タブ
使用する、**グローバル設定** タブで使用されるログ ストアを構成する[!INCLUDE[HL7_CurrentVersion_FirstRef](../../includes/hl7-currentversion-firstref-md.md)]です。  
  
 **BTAHL7 構成エクスプ ローラー**  ダイアログ ボックスで、**グローバル設定** タブで、次の操作します。  
  
|プロパティ|目的|  
|--------------|----------------|  
|**WMI**|生成する場合は、このオプションを選択[!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)]BTAHL7 の Management Instrumentation (WMI) 通知します。|  
|**SQL**|使用する場合は、このオプションを選択[!INCLUDE[btsCoName](../../includes/btsconame-md.md)] [!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)] BTAHL7 のログ ストアとして。 **注:** BTAHL7 が存在しない場合は、ログに必要なテーブルを自動的に作成します。|  
|**SQL Server**|型、[!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)]名。 これは、選択したときに必要な**SQL**オプション。 許容最大長は、64 文字です。<br /><br /> 既定のサーバーとデータベース名は、構成された BTAHL7 データベースです。|  
|**データベース名**|型、[!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)]データベース名。 これは、選択したときに必要な**SQL**オプション。 許容最大長は、128 文字です。|  
|**イベント ログ**|使用する場合は、このオプションを選択、 [!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)] BTAHL7 のログ ストアとしてのイベント ログです。 使用する、[!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)]イベント メッセージを表示するイベント ビューアー。|