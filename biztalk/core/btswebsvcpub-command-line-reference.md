---
title: BTSWebSvcPub コマンド ライン リファレンス |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 5e19dd4d-9f2c-4a17-9437-8701e1c274fb
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c5d4098478bdb6257bdcfb2ed10b925a26c59d84
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65357800"
---
# <a name="btswebsvcpub-command-line-reference"></a>BTSWebSvcPub コマンド ライン リファレンス
このトピックでは、付属の BTSWebSvcPub コマンド ライン ツールに関するリファレンス情報を提供します。[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]します。 次のように Web サービスからオーケストレーションを公開するため、Web サービス (.asmx) を作成するのに BTSWebSvcPub を使用できます。  
  
## <a name="usage"></a>使用方法  
 **BTSWebSvcPub PathName [-Location:** *value* **] [-Overwrite] [-Anonymous]**  
  
 **[-Name:** *value* **] [-Namespace:** *value* **] [-TargetNamespace:** *value* **]**  
  
 **[-UnknownHeaders[** *+* **&#124;** *-* **]] [-SingleSignOn[** *+* **&#124;** *-* **]] [-ParameterStyle:** *value* **]**  
  
 **[-ConformanceClaims:** *value* **] [-ForceRequestResponse:** *value* **] [-ReceiveLocation]**  
  
 **[-ApplicationName:** *value* **]**  
  
## <a name="parameters"></a>パラメーター  
  
|         パラメーター         | 必須 |                                                           説明                                                            |
|---------------------------|----------|----------------------------------------------------------------------------------------------------------------------------------|
|       **PathName**        |   はい    |                    BizTalk アセンブリのパスとファイル名 (\*.dll) または web サービスの説明 (\*.xml) ファイル。                     |
|       **-Location**       |    いいえ    |                                 公開先の場所です。 (構文:"http://host[: ポート]/パス")                                 |
|      **-上書き**       |    いいえ    |                                                  指定した場所を上書きします。                                                   |
|      **匿名**       |    いいえ    |                                              Web サービスへの匿名アクセスを許可します。                                              |
|         **-Name**         |    いいえ    |                    ソリューションと Web サービスを含むアセンブリ (.sln ファイルと .dll ファイル) の名前。                    |
|      **-Namespace**       |    いいえ    |                                             Web サービス コードの既定の名前空間。                                              |
|   **-Targetnamespace**    |    いいえ    |                        Web サービスのターゲット名前空間。 (例:'<http://www.northwindtraders.com>')                        |
|    **-UnknownHeaders**    |    いいえ    |                                                  不明な SOAP ヘッダーをサポートします。                                                   |
|    **-SinglesSignon**     |    いいえ    |                                  SharePoint Portal Server シングル サインオン SOAP ヘッダーをサポートします。                                   |
|    **-ParameterStyle**    |    いいえ    |                               メッセージの soapparameterstyle です。"Default"、"Bare"、または「ラップ」します。                               |
|  **-ConfirmanceClaims**   |    いいえ    |                              Web services interoperability (WSI) の要求:"None"または"BasicProfile1_1"。                              |
| **-ForceRequestResponse** |    いいえ    |                                要求-応答 web メソッドとしては、一方向の BizTalk 操作を公開します。                                |
|   **-ReceiveLocation**    |    いいえ    |                                  作成する受信場所を指定された BizTalk アプリケーションにします。                                  |
|   **-ApplicationName**    |    いいえ    | 受信場所を作成する BizTalk アプリケーションの名前。 指定されていない場合は、既定の BizTalk アプリケーションが使用されます。 |
  
## <a name="sample"></a>サンプル  
 BTSWebSvcPub.exe "MyAssembly.dll" -Location:<http://localhost/MyVdir>  
  
 -上書き  
  
## <a name="remarks"></a>コメント  
 パラメーター名は大文字小文字は区別されず、省略することがあります。 パラメーター値は大文字と小文字が区別されます。  
  
## <a name="see-also"></a>参照  
 [BizTalk Web サービス公開ウィザードを使用して、オーケストレーションを Web サービスとして公開する方法](../core/publish-orchestration-as-web-service--biztalk-web-services-publishing-wizard.md)