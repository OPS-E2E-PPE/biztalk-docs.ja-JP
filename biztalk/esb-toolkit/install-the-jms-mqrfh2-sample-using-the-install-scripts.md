---
title: インストール スクリプトを使用して、JMS MQRFH2 サンプルのインストール |Microsoft Docs
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
ms.openlocfilehash: 8dfde04d2f4b9faebabbac102f938839596540af
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65399884"
---
# <a name="install-the-jms-mqrfh2-sample-using-the-install-scripts"></a>インストール スクリプトを使用して、JMS MQRFH2 サンプルをインストールします。
このセクションでは、付属のインストール スクリプトを使用して、JMS MQRFH2 サンプルをインストールする方法について説明します、[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]します。  
  
 **インストール スクリプトから JMS MQRFH2 サンプルをインストールするには**  
  
1.  名前のキュー マネージャーを作成する WebSphere エクスプ ローラーを使用して**ESB します。JMS します。Sample.QueueManager**します。  
  
2.  内で次の 4 つのキューを作成して WebSphere エクスプ ローラーを使用して**ESB します。JMS します。Sample.QueueManager:**  
  
    -   ESB します。JMS します。サンプルです。DYNAMICQ1  
  
    -   ESB します。JMS します。サンプルです。DYNAMICQ2  
  
    -   ESB します。JMS します。サンプルです。応答  
  
    -   ESB します。JMS します。サンプルです。SENDTOBIZTALK  
  
3.  **[スタート]** メニューの **[ファイル名を指定して実行]** をクリックします。  
  
4.  **実行**ダイアログ ボックスに「 **cmd**、し、ENTER キーを押します。  
  
5.  次のコマンドを実行して交換、 *\<パス\>* をインストールする .cmd ファイルへの完全パスを持つパラメーター (このリリースでは既定のパスは \Source\Samples\JMS\Install\Scripts\\):  
  
    ```  
    <path>\Setup_bin.cmd  
    ```