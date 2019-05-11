---
title: パスワード同期を構成する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Password Synchronization [SSO], replay files
- Password Synchronization [SSO], maximum age
- SSOCONFIG command line utility
- Password Synchronization [SSO], SSOCONFIG command line utility
- Password Synchronization [SSO], configuring
- configuring, Password Synchronization [SSO]
ms.assetid: 04000dfc-02b9-4d50-babe-8bc8a07a33b7
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b1b18d6f59b364a12a9ffe775d64a57e310f76e9
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65341299"
---
# <a name="how-to-configure-password-synchronization"></a>パスワード同期を構成する方法
SSOCONFIG コマンド ライン ユーティリティを使用して、パスワード同期設定を構成します。  
  
### <a name="to-specify-the-directory-for-replay-files"></a>再生ファイルのディレクトリを指定するには  
  
1.  **[スタート]** メニューの **[ファイル名を指定して実行]** をクリックします。  
  
2.  **実行**ダイアログ ボックスに「 **cmd**、順にクリックします**OK**します。  
  
3.  コマンド ラインで、エンタープライズ シングル サインオンのインストール ディレクトリに移動します。 既定値は\<ドライブ\>: \Program Files\Common \enterprise シングル サインオンします。  
  
4.  型**ssoconfig-replayfiles\<再生ファイル ディレクトリ\> &#124; -既定**Enter キーを押します。  
  
> [!NOTE]
>  サービス アカウントを変更すると、再生ファイルは削除されません。 このアカウントを変更する場合は、再生ファイルを手動で削除する必要があります。  
  
#### <a name="to-display-or-change-maximum-password-synchronization-age"></a>表示またはパスワード同期の有効期間を変更するには  
  
1.  **[スタート]** メニューの **[ファイル名を指定して実行]** をクリックします。  
  
2.  **実行**ダイアログ ボックスに「 **cmd**、順にクリックします**OK**します。  
  
3.  コマンド ラインで、エンタープライズ シングル サインオンのインストール ディレクトリに移動します。 既定値は\<ドライブ\>: \Program Files\Common \enterprise シングル サインオンします。  
  
4.  型**ssoconfig-syncage」\<パスワードの最大保有期間を時間で\>** Enter キーを押します。  
  
> [!NOTE]
>  SSOCONFIG ユーティリティは、システム時刻として SQL Server コンピューターの時刻を使用します。 時間に関連するコマンドを使用する場合は、このオプションを思い出してください。  
  
## <a name="see-also"></a>参照  
 [パスワード同期](../core/password-synchronization2.md)