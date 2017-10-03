---
title: "BTSWebSvcPub コマンド ライン リファレンス |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 5e19dd4d-9f2c-4a17-9437-8701e1c274fb
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9c9993092c0d798ae2d47f614a24da21c3a2df62
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="btswebsvcpub-command-line-reference"></a>BTSWebSvcPub コマンド ライン リファレンス
ここでは、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] に付属の BTSWebSvcPub コマンド ライン ツールに関するリファレンス情報を提供します。 BTSWebSvcPub を使用して、次に示すように、Web サービスからオーケストレーションを公開するための Web サービス (.asmx) を作成することができます。  
  
## <a name="usage"></a>使用方法  
 **BTSWebSvcPub PathName [-場所:** *値* **] [の上書き] [-匿名]**  
  
 **[-名:** *値* **] [-Namespace:** *値* **] [-TargetNamespace:** *値* **]**  
  
 **[-UnknownHeaders [**  *+*  **&#124;** *-*  **] [-SingleSignOn [**  *+*  **&#124;** *-*  **] [-ParameterStyle:** *値* **]**  
  
 **[-ConformanceClaims:** *値* **] [-ForceRequestResponse:** *値* **] [-受信場所]**  
  
 **[-ApplicationName:** *値* **]**  
  
## <a name="parameters"></a>パラメーター  
  
|パラメーター|必須|Description|  
|---------------|--------------|-----------------|  
|**PathName**|はい|BizTalk アセンブリ (*.dll) または web サービスの説明のパスとファイル名 (\*.xml) ファイル。|  
|**-場所**|不可|公開する場所。 (構文: "http://host[:port]/path")|  
|**-上書き**|不可|指定した場所を上書きします。|  
|**匿名**|不可|Web サービスへの匿名アクセスを許可します。|  
|**名**|不可|Web サービスを含めるソリューションおよびアセンブリ (.sln ファイルおよび .dll ファイル) の名前です。|  
|**-Namespace**|不可|Web サービス コードの既定の名前空間。|  
|**-Targetnamespace**|不可|Web サービスの対象となる名前空間。 (例: 'http://www.northwindtraders.com')|  
|**-UnknownHeaders**|不可|不明な SOAP ヘッダーをサポートします。|  
|**-SinglesSignon**|不可|SharePoint Portal Server のシングル サインオン SOAP ヘッダーをサポートします。|  
|**-ParameterStyle**|不可|メッセージの soapparameterstyle です:"Default"、"Bare"または"Wrapped"です。|  
|**-ConfirmanceClaims**|不可|要求の web サービスの相互運用性 (WSI):"None"または"basicprofile1_1 を指定"します。|  
|**-ForceRequestResponse**|不可|一方向の BizTalk 操作を、要求 - 応答 Web メソッドとして公開します。|  
|**-受信場所**|不可|指定された BizTalk アプリケーションに受信場所を作成します。|  
|**-ApplicationName**|不可|受信場所を作成する BizTalk アプリケーションの名前。 指定しなかった場合、既定の BizTalk アプリケーションが使用されます。|  
  
## <a name="sample"></a>サンプル  
 BTSWebSvcPub.exe "MyAssembly.dll" -Location:http://localhost/MyVdir  
  
 -Overwrite  
  
## <a name="remarks"></a>解説  
 パラメータ名では大文字と小文字は区別されません。省略したパラメータ名は使用できます。 パラメーター値は大文字と小文字が区別されます。  
  
## <a name="see-also"></a>参照  
 [BizTalk Web サービス公開ウィザードを使用してオーケストレーションを Web サービスとして公開する方法](../core/publish-orchestration-as-web-service--biztalk-web-services-publishing-wizard.md)