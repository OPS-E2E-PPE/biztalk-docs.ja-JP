---
title: 側開始 SSO のホストで Trace ユーティリティを使用する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- host initiated SSO, trace utility
- trace utility
ms.assetid: a53444d1-3f63-42a6-8ee6-b60ff9af9e41
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ed0b0a77881cba6de26454f51c6f6f8e21103e90
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65333170"
---
# <a name="how-to-use-the-trace-utility-in-host-initiated-sso"></a>側開始 SSO のホストで Trace ユーティリティを使用する方法
トラブルシューティングの主要な方法をトレースしています。  
  
## <a name="tracing"></a>追跡  
 SSO でトレースを有効にするのにには、トレースのコマンド ライン ユーティリティを使用します。  
  
> [!NOTE]
>  トレース コマンドが動作する次のディレクトリにファイル tracelog.exe 必要があります。  
>   
>  \<*drive*\>:\Program Files\Common Files\Enterprise Single Sign-On  
  
> [!NOTE]
>  このファイルは、次の場所からダウンロードできます。 [http://go.microsoft.com/fwlink/?LinkId=59534](http://go.microsoft.com/fwlink/?LinkId=59534)  
  
#### <a name="to-use-the-trace-utility"></a>トレース ユーティリティを使用するには  
  
1.  **[スタート]** メニューの **[ファイル名を指定して実行]** をクリックします。  
  
2.  **実行**ダイアログ ボックスに「 **cmd**、順にクリックします**OK**します。  
  
3.  コマンド ラインで、エンタープライズ シングル サインオンのインストール ディレクトリに移動します。 既定値は\<ドライブ\>: \Program Files\Common \enterprise シングル サインオンします。  
  
4.  型**Trace – start – high**高 に、トレース レベルを設定し、トレースを開始します。  
  
5.  側開始 SSO のホストでシナリオを実行します。  
  
6.  型**Trace – 停止**トレースを終了します。 ディレクトリの上、分析のため Microsoft に送信することができますに .bin ファイルが生成されます。  
  
## <a name="see-also"></a>参照  
 [ホスト側開始 SSO](../core/host-initiated-sso.md)