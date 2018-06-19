---
title: ExportSettings コマンド |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: fa34dab1-c854-473e-a693-43ba45624e16
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ab8c39ef6903affbd2a1446bbde18a56e1a7778c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22245946"
---
# <a name="exportsettings-command"></a>ExportSettings コマンド
ExportSettings コマンドでは、BizTalk Server 設定を BizTalk Server 構成データベースから XML ファイルにエクスポートできます。 別の環境でこれらの設定をインポートすることができますし、[インポート BizTalk の設定を使用して設定ダッシュ ボード方法](../core/how-to-import-biztalk-settings-using-settings-dashboard.md)または[BTSTask を使用して BizTalk の設定をインポートする方法](../core/how-to-import-biztalk-settings-using-btstask.md)です。  
  
## <a name="prerequisites"></a>前提条件  
 ここで示す操作を実行するには、BizTalk Server 管理者グループのメンバーとしてログオンする必要があります。  
  
## <a name="usage"></a>使用方法  
 `ExportSettings –Destination:value[-Server:value] [-Database:value]`  
  
## <a name="parameters"></a>パラメーター  
  
|**パラメーター**|必須|値|  
|-------------------|--------------|-----------|  
|**変換先**|はい|書き込み先 XML ファイルのパスとファイル名。|  
|**-サーバー**|省略可|BizTalk 構成データベースをホストしている SQL Server の名前。|  
|**複数のデータベース**|省略可|BizTalk 構成データベースの名前。|  
  
## <a name="sample"></a>サンプル  
 `BTSTask ExportSettings /Destination:MyFile.xml /Server:MyServer /Database:MyMgmtDb`  
  
## <a name="remarks"></a>解説  
 パラメーターの大文字と小文字は区別されません。 パラメーター名は、すべて入力する必要はありません。最初の数文字 (一意に特定できるだけの文字数) を入力するだけで構いません。  
  
## <a name="see-also"></a>参照  
 [BTSTask コマンド ライン リファレンス](../core/btstask-command-line-reference.md)