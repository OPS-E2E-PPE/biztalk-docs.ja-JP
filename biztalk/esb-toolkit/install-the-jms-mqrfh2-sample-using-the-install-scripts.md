---
title: インストール スクリプトを使用して、JMS MQRFH2 サンプルのインストール |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 785f3e32-83b4-406a-af1b-9499115fbb8f
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: edb3102fabc84818cb42fcdcba6a034d085bdcc4
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
ms.locfileid: "25974384"
---
# <a name="install-the-jms-mqrfh2-sample-using-the-install-scripts"></a>インストール スクリプトを使用して、JMS MQRFH2 サンプルをインストールします。
このセクションでは、JMS MQRFH2 で提供するインストール スクリプトを使用してサンプルをインストールする方法について説明します、[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]です。  
  
 **インストール スクリプトから JMS MQRFH2 サンプルをインストールするには**  
  
1.  名前のキュー マネージャーを作成する WebSphere エクスプ ローラーを使用して**ESB です。JMS です。Sample.QueueManager**です。  
  
2.  次の 4 つのキュー内で WebSphere エクスプ ローラーを使用して作成**ESB です。JMS です。Sample.QueueManager:**  
  
    -   ESB です。JMS です。サンプルです。DYNAMICQ1  
  
    -   ESB です。JMS です。サンプルです。DYNAMICQ2  
  
    -   ESB です。JMS です。サンプルです。応答  
  
    -   ESB です。JMS です。サンプルです。SENDTOBIZTALK  
  
3.  **[スタート]** メニューの **[ファイル名を指定して実行]** をクリックします。  
  
4.  **実行** ダイアログ ボックスで、「 **cmd**、ENTER キーを押します。  
  
5.  次のコマンド実行交換、 *\<パス\>* をインストールする .cmd ファイルへの完全パスを持つパラメーター (このリリースでは既定のパスは \Source\Samples\JMS\Install\Scripts\\):  
  
    ```  
    <path>\Setup_bin.cmd  
    ```