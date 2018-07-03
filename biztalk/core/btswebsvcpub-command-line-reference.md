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
ms.openlocfilehash: 62df9b42a9bc709275c836ed2d670d017b217ef6
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36980443"
---
# <a name="btswebsvcpub-command-line-reference"></a>BTSWebSvcPub コマンド ライン リファレンス
ここでは、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] に付属の BTSWebSvcPub コマンド ライン ツールに関するリファレンス情報を提供します。 BTSWebSvcPub を使用して、次に示すように、Web サービスからオーケストレーションを公開するための Web サービス (.asmx) を作成することができます。  
  
## <a name="usage"></a>使用方法  
 **BTSWebSvcPub パス名 [-場所:** *値* **] [-上書き] [-匿名]**  
  
 **[-名:** *値* **] [-Namespace:** *値* **] [-TargetNamespace:** *値* **]**  
  
 **[-UnknownHeaders [** *+* **&#124;** *-* **] [-SingleSignOn [** *+*  **&#124;** *-* **] [-ParameterStyle:** *値***]**  
  
 **[-ConformanceClaims:** *値* **] [-ForceRequestResponse:** *値* **] [-受信場所]**  
  
 **[-ApplicationName:** *値* **]**  
  
## <a name="parameters"></a>パラメーター  
  
|         パラメーター         | 必須 |                                                           説明                                                            |
|---------------------------|----------|----------------------------------------------------------------------------------------------------------------------------------|
|       **PathName**        |   はい    |                    BizTalk アセンブリのパスとファイル名 (\*.dll) または web サービスの説明 (\*.xml) ファイル。                     |
|       **-場所**       |    いいえ    |                                 公開する場所。 (構文:"http://host[: ポート]/パス")                                 |
|      **-上書き**       |    いいえ    |                                                  指定した場所を上書きします。                                                   |
|      **匿名**       |    いいえ    |                                              Web サービスへの匿名アクセスを許可します。                                              |
|         **-名前**         |    いいえ    |                    Web サービスを含めるソリューションおよびアセンブリ (.sln ファイルおよび .dll ファイル) の名前です。                    |
|      **-Namespace**       |    いいえ    |                                             Web サービス コードの既定の名前空間。                                              |
|   **-Targetnamespace**    |    いいえ    |                        Web サービスの対象となる名前空間。 (例:'<http://www.northwindtraders.com>')                        |
|    **-UnknownHeaders**    |    いいえ    |                                                  不明な SOAP ヘッダーをサポートします。                                                   |
|    **-SinglesSignon**     |    いいえ    |                                  SharePoint Portal Server のシングル サインオン SOAP ヘッダーをサポートします。                                   |
|    **-ParameterStyle**    |    いいえ    |                               メッセージの SoapParameterStyle:"Default"、"Bare"、または"Wrapped"。                               |
|  **-ConfirmanceClaims**   |    いいえ    |                              Web services interoperability (WSI) の要求:"None"または"BasicProfile1_1"。                              |
| **-ForceRequestResponse** |    いいえ    |                                一方向の BizTalk 操作を、要求 - 応答 Web メソッドとして公開します。                                |
|   **-受信場所**    |    いいえ    |                                  指定された BizTalk アプリケーションに受信場所を作成します。                                  |
|   **-ApplicationName**    |    いいえ    | 受信場所を作成する BizTalk アプリケーションの名前。 指定しなかった場合、既定の BizTalk アプリケーションが使用されます。 |
  
## <a name="sample"></a>サンプル  
 BTSWebSvcPub.exe "MyAssembly.dll" -Location:<http://localhost/MyVdir>  
  
 -Overwrite  
  
## <a name="remarks"></a>コメント  
 パラメータ名では大文字と小文字は区別されません。省略したパラメータ名は使用できます。 パラメーター値は大文字と小文字が区別されます。  
  
## <a name="see-also"></a>参照  
 [BizTalk Web サービス公開ウィザードを使用して、オーケストレーションを Web サービスとして公開する方法](../core/publish-orchestration-as-web-service--biztalk-web-services-publishing-wizard.md)