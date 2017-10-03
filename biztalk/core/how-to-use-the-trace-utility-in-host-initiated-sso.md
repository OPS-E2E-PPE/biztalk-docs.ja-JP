---
title: "側開始 SSO のホストで、トレース ユーティリティを使用する方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- host initiated SSO, trace utility
- trace utility
ms.assetid: a53444d1-3f63-42a6-8ee6-b60ff9af9e41
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e00514515b31e79655fe457e1aa8682edf002183
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-use-the-trace-utility-in-host-initiated-sso"></a>側開始 SSO のホストで、トレース ユーティリティを使用する方法
トラブルシューティングの主要な方法はトレースを行うことです。  
  
## <a name="tracing"></a>追跡  
 SSO でトレースを有効にするには Trace コマンド ライン ユーティリティを使用します。  
  
> [!NOTE]
>  Trace コマンドが動作するためには、tracelog.exe ファイルが次のディレクトリに存在する必要があります。  
>   
>  \<*ドライブ*>: \program files \common files \enterprise シングル サインオン  
  
> [!NOTE]
>  このファイルは、次の場所からダウンロードできます: [http://go.microsoft.com/fwlink/?LinkId=59534](http://go.microsoft.com/fwlink/?LinkId=59534)  
  
#### <a name="to-use-the-trace-utility"></a>Trace ユーティリティを使用するには  
  
1.  **[スタート]** メニューの **[ファイル名を指定して実行]**をクリックします。  
  
2.  **実行** ダイアログ ボックスで、「 **cmd**、順にクリック**OK**です。  
  
3.  コマンド ラインで、エンタープライズ シングル サインオンのインストール ディレクトリに移動します。 既定値は\<ドライブ >: \program files \common files \enterprise シングル サインオンします。  
  
4.  型**Trace – start – 高**高 に、トレース レベルを設定し、トレースを開始します。  
  
5.  ホスト側開始 SSO でシナリオを実行します。  
  
6.  型**Trace – 停止**トレースを終了します。 .bin ファイルが上記のディレクトリに生成されます。このファイルは、分析のためにマイクロソフトに送信することができます。  
  
## <a name="see-also"></a>参照  
 [ホスト側開始 SSO](../core/host-initiated-sso.md)