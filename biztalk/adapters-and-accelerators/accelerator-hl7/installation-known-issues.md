---
title: 既知の問題のインストール |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b2f80ff9-b37c-49f8-8250-fcf3cec4c0fc
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bf4e9197d2b3c448b4fd9cc42c0cdeb929917061
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22204546"
---
# <a name="installation-known-issues"></a>インストールの既知の問題
役立つ有用な情報は、インストールの問題を回避します。  
  
## <a name="prerequisites-for-installing-btahl7"></a>BTAHL7 をインストールするための前提条件  
 インストールの前提条件[!INCLUDE[btaBTAHL7NoNumber](../../includes/btabtahl7nonumber-md.md)]次のとおりです。  
  
-   基本コンポーネント[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]、エンタープライズ シングル サインオン (SSO)、グループ、およびランタイムを含め、構成する必要があります。  
  
-   インストールして、BTAHL7 を構成するユーザーは、BizTalk 管理者グループのメンバーであり、BTAHL7 データが格納されている SQL Server の Administrators グループのメンバーにする必要があります。
  
## <a name="sql-server-mixed-mode-not-supported"></a>SQL Server 混在モードがサポートされていません  
[!INCLUDE[btaBTAHL7NoNumber](../../includes/btabtahl7nonumber-md.md)]混在モードで SQL Server をサポートしていません。  
  
## <a name="repair-does-not-work-from-uninstallchange"></a>修復はアンインストールと変更からは機能しません  
ユーザー アクセス制御 (UAC) が有効になっているし、コントロール パネルを使用して、インストールを修復しようとする、修復は失敗します。 

Microsoft では、UAC が有効にしておくことをお勧めします。

 **解決策**  
  
 実行、[!INCLUDE[btaBTAHL7NoNumber](../../includes/btabtahl7nonumber-md.md)]クリックし、setup.exe**修復**です。  
  
## <a name="see-also"></a>参照  
[インストールまたは Microsoft BizTalk Accelerator 用 HL7 にアップグレード](../../adapters-and-accelerators/accelerator-hl7/install-or-upgrade-microsoft-biztalk-accelerator-for-hl7.md)