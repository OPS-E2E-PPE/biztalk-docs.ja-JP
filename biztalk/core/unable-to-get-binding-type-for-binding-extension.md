---
title: バインド拡張機能のバインドの種類を取得できません |。Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 5a7cfc81-7439-48f9-8cac-42b2419ecd9d
caps.latest.revision: 20
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 15a55bc8f06465daec562624866ed41a43059a05
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65292789"
---
# <a name="unable-to-get-binding-type-for-binding-extension"></a>バインド拡張機能のバインドの種類を取得できません
## <a name="details"></a>詳細  

|                 |                                                                                                                                                                                                                                  |
|-----------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  製品名   |                                                                        [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                                                                        |
| 製品バージョン |                                                                                    [!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]                                                                                    |
|    イベント ID     |                                                                                                                0                                                                                                                 |
|  イベント ソース   |                                                                                                                0                                                                                                                 |
|    コンポーネント    |                                                                                                                0                                                                                                                 |
|  シンボル名  |                                                                                                                0                                                                                                                 |
|  メッセージ テキスト   | バインド拡張機能のバインドの種類を取得できません。"{0}"。 Machine.config が更新されたは、アプリケーションが開いているときに場合、は、変更内容を取得するアプリケーションを再起動します。 バインド拡張機能が machine.config に登録されていることを確認します。 |

## <a name="explanation"></a>説明  
 Wcf-custom または Wcf-customisolated トランスポートのカスタム バインド拡張機能が正しく構成されていません。  

## <a name="user-action"></a>ユーザーの操作  
 このエラーは解決するのには、次の 1 つ以上の操作を行います。  

- 確認、 **machine.config ファイル**で **%WinDir%\Microsoft.NET\Framework\v4.0.30319\Config**が、 \< **bindingExtensions** \>要素が適切に構成します。  

- Windows エクスプ ローラーに移動 **%WinDir%\Assembly**、カスタム バインド拡張機能を実装するアセンブリが正しくインストールされているかどうかを確認します。  

- WCF カスタム アダプターの場合、BizTalk 管理コンソールで、WCF トランスポートを実行するホスト インスタンスを再起動します。  

- Wcf-customisolated アダプターの場合、IIS 管理コンソールで、WCF トランスポートをホストしているアプリケーション プールを再起動します。  

- 開かれた場合、BizTalk 管理コンソールの開閉  

  詳細については、次のリソースを参照してください。  

- [WCF アダプターで WCF 機能拡張ポイントを有効にする方法](../core/how-to-enable-the-wcf-extensibility-points-with-the-wcf-adapters.md)
