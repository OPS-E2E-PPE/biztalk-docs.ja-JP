---
title: パスワード同期を構成する方法 |Microsoft ドキュメント
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
ms.openlocfilehash: b2e8348cdf78db3e95ed75e5d83e6ea53bdffdee
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
ms.locfileid: "25968912"
---
# <a name="how-to-configure-password-synchronization"></a>パスワード同期を構成する方法
SSOCONFIG コマンド ライン ユーティリティを使用すると、パスワード同期の設定を構成できます。  
  
### <a name="to-specify-the-directory-for-replay-files"></a>再生ファイルのディレクトリを指定するには  
  
1.  **[スタート]** メニューの **[ファイル名を指定して実行]** をクリックします。  
  
2.  **実行** ダイアログ ボックスで、「 **cmd**、順にクリック**OK**です。  
  
3.  コマンド ラインで、エンタープライズ シングル サインオンのインストール ディレクトリに移動します。 既定値は\<ドライブ\>: \program files \common files \enterprise シングル サインオンします。  
  
4.  型**ssoconfig-replayfiles\<再生ファイル ディレクトリ\>(& a) #124; 既定**Enter キーを押します。  
  
> [!NOTE]
>  サービス アカウントを変更すると、再生ファイルは検出されません。 このアカウントを変更する場合、再生ファイルを手動で削除することが必要になります。  
  
#### <a name="to-display-or-change-maximum-password-synchronization-age"></a>パスワード同期の最大有効期間を表示または変更するには  
  
1.  **[スタート]** メニューの **[ファイル名を指定して実行]** をクリックします。  
  
2.  **実行** ダイアログ ボックスで、「 **cmd**、順にクリック**OK**です。  
  
3.  コマンド ラインで、エンタープライズ シングル サインオンのインストール ディレクトリに移動します。 既定値は\<ドライブ\>: \program files \common files \enterprise シングル サインオンします。  
  
4.  型**ssoconfig-syncage\<パスワードの最大保有期間を時間で\>** Enter キーを押します。  
  
> [!NOTE]
>  SSOCONFIG ユーティリティでは、システム時刻として SQL Server コンピュータの時刻を使用します。 時刻に関連するコマンドを使用する際は、このことに注意してください。  
  
## <a name="see-also"></a>参照  
 [パスワード同期](../core/password-synchronization2.md)