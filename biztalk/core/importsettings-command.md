---
title: "ImportSettings コマンド |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 587f7e1f-9cf7-4e7b-90cd-11a266f474dc
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9c609634422f8c8b5f2c1a96691fe4eda708e5c9
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="importsettings-command"></a>ImportSettings コマンド
BizTalk グループ、ホスト、またはホスト インスタンスの設定を、送信元 XML ファイルから構成データベースにインポートします。 設定は、マッピング XML ファイル内にある場合と同じようにマップされます。 これらの設定はエクスポートされている」の説明に従って[インポートまたはエクスポート BizTalk の設定を使用して設定のダッシュ ボード](how-to-import-biztalk-settings-using-settings-dashboard.md)または[インポートまたはエクスポート BizTalk の設定を使用して BTSTask](how-to-import-biztalk-settings-using-btstask.md)です。  
  
## <a name="prerequisites"></a>前提条件  
 この操作を実行するには、BizTalk Server 管理者グループのメンバーとしてサインインする必要があります。  
  
## <a name="usage"></a>使用方法  
 `ImportSettings –Source:value –Map: value [-Server:value] [-Database:value]`  
  
## <a name="parameters"></a>パラメーター  
  
|**パラメーター**|必須|値|  
|-------------------|--------------|-----------|  
|**ソース**|はい|エクスポートされた設定 XML ファイルのパスとファイル名。|  
|**マップ**|はい|マッピング XML ファイルのパスとファイル名。|  
|**-サーバー**|省略可|BizTalk 構成データベースをホストする SQL Server コンピューターの名前。|  
|**複数のデータベース**|省略可|BizTalk 構成データベースの名前。|  
  
## <a name="sample"></a>サンプル  
 `BTSTask ImportSettings /Source:”C:\My Folder>\ExportedSettings.xml” /Map:Mappings.xml /Server:MyServer /Database:MyMgmtDb`  
  
## <a name="remarks"></a>解説  
 パラメーターの大文字と小文字は区別されません。 パラメーター名は、すべて入力する必要はありません。最初の数文字 (一意に特定できるだけの文字数) を入力するだけで構いません。  
  
## <a name="see-also"></a>参照  
 [BTSTask コマンド ライン リファレンス](../core/btstask-command-line-reference.md)