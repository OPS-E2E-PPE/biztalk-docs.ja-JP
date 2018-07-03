---
title: COM + 修正プログラム ロールアップ パッケージをインストールする |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 587ae3da-db65-4da8-9d3b-89effb91b197
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 110dced7d3931e1987ccf966efffb700e1c5555b
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37020520"
---
# <a name="installing-com-hotfix-rollup-packages"></a>COM + 修正プログラム ロールアップ パッケージをインストールします。
> [!NOTE]  
>  このトピックでは、Windows Server 2003 にのみ適用できます。  
  
 最後のバージョンの Windows Server 2003 の COM + 修正プログラム ロールアップ パッケージと分散トランザクション コーディネーター (DTC) のプログラムのロールアップ パッケージの最新バージョンをインストールする必要があります。 これは、パッケージには、多くのパフォーマンスと安定性の修正が含まれているためにです。  
  
 これらのプログラムのロールアップを実行しているすべてのコンピューターにインストールしてください[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]とすべてのコンピューターで SQL Server を実行します。 プログラムのロールアップは、高スループットのシナリオで適切に動作する BizTalk ソリューションにとって特に重要です。  
  
 修正されました DTC の問題は次のとおりです。  
  
- DTC の予期しないシャット ダウン  
  
- メモリの断片化の問題  
  
- DTC が負荷の下で応答を停止する可能性があります。  
  
- 使用すると、応答を停止またはメモリ リークが発生 DTC [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]  
  
- 負荷の下で DTC のパフォーマンスが改善されました  
  
## <a name="installing-the-com-rollup-package"></a>COM + ロールアップ パッケージをインストールします。  
 COM + ロールアップ パッケージは不要になったリリースします。 最後の COM + のパッケージをインストールするには、この情報に従います。  
  
-   COM + ロールアップの最終バージョンには、"Windows Server 2003 Service Pack 2 COM + 1.5年修正プログラム ロールアップ パッケージ 12年"。 この修正プログラムは、任意のバージョンの service pack がインストールされていないものも含め、Windows Server 2003 にインストールされます。 この修正プログラムの詳細については、マイクロソフト サポート技術情報記事 934016 で参照できます["可用性の Windows Server 2003 Service Pack 2 COM + 1.5年修正プログラム ロールアップ パッケージ 12年"](http://go.microsoft.com/fwlink/?LinkId=158756) (http://go.microsoft.com/fwlink/?LinkId=158756)します。  
  
## <a name="installing-the-dtc-rollup-package"></a>DTC のロールアップ パッケージをインストールします。  
 DTC は、COM + の独立したプログラムのロールアップ パッケージをリリースする予定です。 DTC の最新のパッケージをインストールするためには、この情報に従います。  
  
-   、この記事の執筆時点は、最新の DTC の修正プログラムのロールアップは、「パッケージ 16」です。 この修正プログラムの詳細については、マイクロソフト サポート技術情報記事 958013 で参照できます[「Windows Server 2003 MS DTC の修正プログラム ロールアップ パッケージ 16 で修正された MS DTC の問題の一覧」](http://support.microsoft.com/kb/979919) (http://support.microsoft.com/kb/979919)します。  
  
     検索して最新の DTC の修正プログラム ロールアップ パッケージに関するサポート技術情報の記事が見つかります[ http://support.microsoft.com ](http://support.microsoft.com/) (引用符を含む) という語句。  
  
    ```  
    "MS DTC Hotfix Rollup Package"  
    ```  
  
     次のクエリは、この検索をします。 最新のものを選択します。  
  
     [http://support.microsoft.com/search/default.aspx?query="MS + DTC + 修正プログラム + ロールアップ + パッケージ"](http://support.microsoft.com/search/default.aspx?query=%22MS+DTC+Hotfix+Rollup+Package%22)