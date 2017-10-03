---
title: "COM + の修正プログラム ロールアップ パッケージをインストールする |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 587ae3da-db65-4da8-9d3b-89effb91b197
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 40610c649e00993323adedf0ea29330dd289a0e3
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="installing-com-hotfix-rollup-packages"></a>COM + の修正プログラム ロールアップ パッケージをインストールします。
> [!NOTE]  
>  このトピックでは、Windows Server 2003 にのみ適用します。  
  
 最後のバージョンの Windows Server 2003 の COM + の修正プログラム ロールアップ パッケージと分散トランザクション コーディネーター (DTC) のプログラムのロールアップ パッケージの最新バージョンをインストールする必要があります。 これは、パッケージには、多くのパフォーマンスや安定性の修正が含まれているためです。  
  
 実行しているすべてのコンピューターにこれらのロールアップをインストールする必要があります[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]とすべてのコンピューターで SQL Server を実行します。 ロールアップは、BizTalk ソリューションを高スループットのシナリオでも実行する場合に特に重要です。  
  
 修正された DTC の問題は次のとおりです。  
  
-   DTC の予期しないシャット ダウン  
  
-   メモリの断片化の問題  
  
-   DTC が負荷の下で応答を停止する可能性があります。  
  
-   DTC リークが発生するメモリまたはを使用すると、応答を停止[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]  
  
-   負荷の下での DTC のパフォーマンスが改善されました  
  
## <a name="installing-the-com-rollup-package"></a>COM + ロールアップ パッケージをインストールします。  
 COM + ロールアップ パッケージが不要になったリリースしました。 最後の COM + のパッケージをインストールするには、この情報に従います。  
  
-   COM + ロールアップの最終バージョンは、"Windows Server 2003 Service Pack 2 COM + 1.5年修正プログラム ロールアップ パッケージ 12年"です。 この修正プログラムは、任意のバージョンの service pack がインストールされていないものも含め、Windows Server 2003 にインストールされます。 この修正プログラムの詳細については、Microsoft サポート技術情報記事 934016 で参照できます["の可用性の Windows Server 2003 Service Pack 2 COM + 1.5年修正プログラム ロールアップ パッケージ 12年"](http://go.microsoft.com/fwlink/?LinkId=158756) (http://go.microsoft.com/fwlink/?LinkId=158756)。  
  
## <a name="installing-the-dtc-rollup-package"></a>DTC ロールアップ パッケージをインストールします。  
 DTC は、COM + の独立したプログラムのロールアップ パッケージをリリースする予定です。 DTC の最新のパッケージをインストールするためには、この情報に従います。  
  
-   このドキュメントの作成時点では、最新の DTC の修正プログラムのロールアップは、「パッケージ 16」です。 この修正プログラムの詳細については、Microsoft サポート技術情報記事 958013 で参照できます[「は、Windows Server 2003 MS DTC の修正プログラム ロールアップ パッケージ 16 で修正 MS DTC の問題の一覧」](http://support.microsoft.com/kb/979919) (http://support.microsoft.com/kb/979919).  
  
     最新の DTC の修正プログラム ロールアップ パッケージに関するサポート技術情報の記事を検索によって見つかりますできます[http://support.microsoft.com](http://support.microsoft.com/) (引用符を含む)、句。  
  
    ```  
    "MS DTC Hotfix Rollup Package"  
    ```  
  
     この検索では、次のクエリ。 最新のものを選択します。  
  
     [http://support.microsoft.com/search/default.aspx?query=「MS + DTC + 修正プログラム + ロールアップ + パッケージ」](http://support.microsoft.com/search/default.aspx?query=%22MS+DTC+Hotfix+Rollup+Package%22)