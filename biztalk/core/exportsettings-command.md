---
title: ExportSettings コマンド |Microsoft Docs
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
ms.openlocfilehash: 1a521ec09017e1ea529dbeb097ce119edee69f7e
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65388208"
---
# <a name="exportsettings-command"></a>ExportSettings コマンド
ExportSettings コマンドで、XML ファイルに BizTalk Server の構成から BizTalk Server 設定をエクスポートするデータベースします。 別の環境でこれらの設定をインポートすることができますし、[インポート BizTalk の設定を使用して設定ダッシュ ボード方法](../core/how-to-import-biztalk-settings-using-settings-dashboard.md)または[BTSTask を使用して BizTalk の設定のインポート方法](../core/how-to-import-biztalk-settings-using-btstask.md)。  
  
## <a name="prerequisites"></a>前提条件  
 この操作を実行するには、BizTalk Server 管理者グループのメンバーとしてログオンする必要があります。  
  
## <a name="usage"></a>使用方法  
 `ExportSettings –Destination:value[-Server:value] [-Database:value]`  
  
## <a name="parameters"></a>パラメーター  
  
|**パラメーター**|必須|値|  
|-------------------|--------------|-----------|  
|**変換先**|はい|書き込む XML ファイルのパスとファイルの名前。|  
|**-サーバー**|省略可|BizTalk 構成データベースをホストする SQL Server の名前。|  
|**-データベース**|省略可|BizTalk 構成データベースの名前。|  
  
## <a name="sample"></a>サンプル  
 `BTSTask ExportSettings /Destination:MyFile.xml /Server:MyServer /Database:MyMgmtDb`  
  
## <a name="remarks"></a>コメント  
 パラメーターの大文字と小文字は区別されません。 パラメーター名は、すべて入力する必要はありません。最初の数文字 (一意に特定できるだけの文字数) を入力するだけで構いません。  
  
## <a name="see-also"></a>参照  
 [BTSTask コマンド ライン リファレンス](../core/btstask-command-line-reference.md)